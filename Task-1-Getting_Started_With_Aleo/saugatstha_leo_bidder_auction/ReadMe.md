# Getting Started with ALEO:

## Create new project:
- Command:
    ```sh
    leo new saugatstha_leo_bidder_auction
    ```

- Create 3 accounts. Owner, Bidder1, Bidder2.
- Command:
    ```sh
    snarkos account new
    ```
- So, run above command 3 times in terminal:
    <details><summary> Detailed Output </summary><blockquote>

    ~~~
    $ snarkos account new

    Private Key  <redacted>
        View Key  <redacted>
        Address  aleo1rdszsdqcm3y0fztxzhpzqydqs07qgmtatl9slypyl0hw8lxpnyxqlrt2ct

    $ snarkos account new

    Private Key  <redacted>
        View Key  <redacted>
        Address  aleo12wgjumuumwjtf5djw7x38j9qpy3e4cs357xl9efpty507jpcgvysy5g66k

    $ snarkos account new

    Private Key  <redacted>
        View Key  <redacted>
        Address  aleo1ntg2wewwf0l3yuulkjnua4lsukf0zujxrrqkharkxq4eat0axsqq42r3gn
    ~~~
    
    </blockquote></details>

- In above output, suppose 1 a/c with Address `aleo1rdszsdqcm3y0fztxzhpzqydqs07qgmtatl9slypyl0hw8lxpnyxqlrt2ct` is owner and remaining 2nd and 3rd a/cs are bidders. 
- Make sure `ENDPOINT` in `.env` file is `https://api.explorer.provable.com/v1`.
     
## Deploy To Testnet:
- We need ALEO token in each accounts. So load up before moving any further.
- Now, the value of `PRIVATE_KEY` in `.env` must be replaced with the `PRIVATE_KEY` of the Owner.
- Command:
    ```sh
    leo deploy --network testnet -y
    ```
    <details><summary> Detailed Output </summary><blockquote>

    ~~~
    $ leo deploy --network testnet -y
        Base deployment cost for 'saugatstha_leo_bidder_auction.aleo' is 14.504325 credits.

        +------------------------------------+----------------+
        | saugatstha_leo_bidder_auction.aleo | Cost (credits) |
        +------------------------------------+----------------+
        | Transaction Storage                | 3.641000       |
        +------------------------------------+----------------+
        | Program Synthesis                  | 9.863325       |
        +------------------------------------+----------------+
        | Namespace                          | 1.000000       |
        +------------------------------------+----------------+
        | Priority Fee                       | 0.000000       |
        +------------------------------------+----------------+
        | Total                              | 14.504325      |
        +------------------------------------+----------------+

        Your current public balance is 40.549989 credits.

        ✅ Created deployment transaction for 'saugatstha_leo_bidder_auction.aleo'

        Broadcasting transaction to https://api.explorer.provable.com/v1/testnet/transaction/broadcast...

        ⌛ Deployment at19rza6geypltjz0ml40uxcvz2javx7h9fyt4j3u2cu2gr2dptvvqqms2chd ('saugatstha_leo_bidder_auction.aleo') has been broadcast to https://api.explorer.provable.com/v1/testnet/transaction/broadcast.

    ~~~

    </blockquote></details>


- On-Chain Outputs: 
    - Deployment ID: `at19rza6geypltjz0ml40uxcvz2javx7h9fyt4j3u2cu2gr2dptvvqqms2chd`
    - Aleo Program: [https://testnet.aleo.info/program/saugatstha_leo_bidder_auction.aleo](https://testnet.aleo.info/program/saugatstha_leo_bidder_auction.aleo)
    - Deploy Txn: [https://testnet.aleo.info/transaction/at19rza6geypltjz0ml40uxcvz2javx7h9fyt4j3u2cu2gr2dptvvqqms2chd](https://testnet.aleo.info/transaction/at19rza6geypltjz0ml40uxcvz2javx7h9fyt4j3u2cu2gr2dptvvqqms2chd) 


## Execution Details:
- 1st Bidder Execution:
    - Transition ID: `au1d55k4m7vucdnqxmh5a99acczeyetscydvc3ck5804vfff6ggpvgqw3e9qk`
    - Output Record: `record1qyqsq80ryg33n52jzujq4cp4zv4m4ccux9kc55jqug3a8yc2ne4l6rqzqvrxy6tyv3jhyscqqgpqpcj4clcjunmpqjwl7xw6cz4xk6xne4x9ymxylvhlnsvev0k0xhcdkuv5ch8a7rcsd23s7xv4k22ernh0sw9dq3hfl6xx6406hz0xluqsvctdda6kuaprqqpqzqrfgczzcfth5r94x3f2zzu5gsmpjyjsgvxv0slrdyaq8chwlw54pqykju6lwa5kumn9wg3sqqspqrl6w6f948dewv4j6vufh3rnn3ncd6pgqec9kf59cmce6wz502lqvx95yn9lqz4grh8d46gkcx6hguyz0ln869thrt08glm6dzc960gjd3sz68`

- 2nd Bidder Execution:
    - Transition ID: `au1hladecqunyznj9fj8txnkf4vj5dl8gtvuycrmfg78rcxyqutu5gqujsd8q`
    - Output Record: `record1qyqspejppqh7gjzdnlspswand02yslta0wu6585jsswnh9vqx3zmhdcvqvrxy6tyv3jhyscqqgpqp52hepd87hc37pqp6l9avy3668e9s2syfnjnasjj2xldj2vxrlgzetkmrdzafd2jn5v329yyyxga54uxhjdudatf0h6urmmjy6ptryxsvctdda6kuaprqqpqzqz4mf07j9zcy8d7p2xp4kv8l6y3jt0dp2tpply5nza35nw3kd3sqsykju6lwa5kumn9wg3sqqspqrze6x3pdc6cg06gyh0rmvn2qcetr3hdrtg3zgf3sk9fac53kmzswlp70lfutnrvzkzwduntl7205ulpxg0rtjs3qtkdv8lu5a2x58gxtxusas`

- Decrypt Record using:
    ```sh
    snarkos developer decrypt -v <VIEW_KEY> -c <RECORD_CIPHERTEXT>
    ```

- Resolve Bid:
    - Transition ID: `au1nqsd78py377qk5rhe9w2z60rmnvr9k0usmcu87rctf96a6qrgqyqcyd5hs`
    - Output Record: `record1qyqspwd84y0zd8uh9s0sw7rwuvl9l3dwfae5kzz0qzeemsn3gkmpvrgxqvrxy6tyv3jhyscqqgpqpeuydg5ama7fzj9cqa3qutxwmc43nkpfram4l8uxc2lkqknd5lgx2g8vhshw8x9tc6v4cmlcjgsx5cjvg85qxj0xqz6tutls45up6ypsvctdda6kuaprqqpqzqy6c97ac7sg600dn30rg40apwlr8m046a7wfnygrp6fhtetzddfqyykju6lwa5kumn9wg3sqqspqp0kvf5rrw6h3ema3ah0g9gd9h5s9unxgfxp8pktf7p7j8hyv2js279l9r4dlcupg6ymwj4x3f56a47ugwd280gkppm0qx8krxc9xegy3v7kxr`

- Finish Bid:
    - Transition ID: `au1g99cpg05d4g50z4w4dvaasnu4tqk3ytkrwf8hdcrntrcjw4tvv8shunxgq`
    - Output Record: `record1qyqspsvzu6j8v8xu9c8u8glpdzuzlmwrk438msewxeuwyd7jw46pzacwqvrxy6tyv3jhyscqqgpqqzcvu6excks6ff8cyucq0g3tllpqzq8qawmw95zdecpaudfkqlgz86sdtx2m0qy3skrnr0lknrumwhydeva54k4apkgcvlgserme55pqvctdda6kuaprqqpqzqrs4zf9l64urfevs0ezd358d3d05qara74a7g67hdh40ewf0fdzzyykju6lwa5kumn9wg3sqqspqz5tn7zmlpekxpucp6sndgsuj73d4gx5dxjv80rgv82hj54syqh39lu4h8weqcyeg2qjd8kpvk8r8ne2yu5mgwnwjtk6uwxymy43rec28hdh4v`

- Claim Bid:
    - Transition ID: `au1sryrhr0gqqkrfwr5jxs6qsqdmf9wrmr5vmksfcptpu3a4t2z85gsey4k7v`
    - Output Record: `record1qyqspvdad0m0spczyfnfs8hhnmkau7nqmwzuhmk6msud64fjx766ynsdqyrxzmt0w4h8ggcqqgqspee6z0l0zeewd7rqlyq6359qt7gx746u0ds2wtug99pssd0tu8gfjeaj6ucd8cyjw5ycfhdfyuk3kjspftymdfvwyj45mzu3wx80qyxq7nr3z7`

# Signature:
## Sign with `true`:
- Command:
    ```sh
    leo account sign --private-key <redacted> --message true
    ```

- Output:
    ```sh
    sign1phy939dk5s3d7g2nzfx5t3w4wq3czujkglyk75k3uszeg5xayypxgruqkeq3cma3paq5hx0s7kzrw0cf80kky3ulgqz8xa54whkcjq3eqq3cj89tatjmwmxa89tme9lwtgzzqh9jt8g4uwtnm2nj98lppwdncktrq4xqtajq8y3sv40wsdtmwppd5lkvz4atxy3w3lqeewhqckjddjs
    ```

## Sign with `Transaction ID`:
- For me, program deployed Transaction ID is: `at19rza6geypltjz0ml40uxcvz2javx7h9fyt4j3u2cu2gr2dptvvqqms2chd`. Command:
    ```sh
    leo account sign -d --private-key <redacted> --message "at19rza6geypltjz0ml40uxcvz2javx7h9fyt4j3u2cu2gr2dptvvqqms2chd" --raw
    ```
- Output:
    ```sh
    sign1kcfqdpuw9m0rg5wuygrhutjepuhmw3zm0qjnmsa6w2fpzp73m5q2tav2pwct2xwtxdppq5n7mrvt20x5qpqn4pxjjjr0ckwgwz4pwqeeqq3cj89tatjmwmxa89tme9lwtgzzqh9jt8g4uwtnm2nj98lppwdncktrq4xqtajq8y3sv40wsdtmwppd5lkvz4atxy3w3lqeewhqclk38ef
    ```