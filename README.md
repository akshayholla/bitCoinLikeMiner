bitCoinLikeMiner
================
File structure:
---build.sbt
--+src
    |
    |-+main
         |
         |-+scala
		|-project1.scala
	 |-+resources
		|-application.conf

How to compile and run the program ?
Answer : We used akka-2.3.6 and scala 2.11.2 and sbt(scala build tool)
----------------
***CHANGE THE IP ADDRESS OF THE MACHINE IN application.conf
EXAMPLE :


-----------------

local machine:
$ sbt
> compile
> run 3

or scala bitCoinMiner 3


remote machine : 
$ sbt
> compile
> run 192.168.1.129

or scala bitCoinMiner 192.168.1.129

Question : Size of the work unit that you determined results in best performance for
your implementation and an explanation on how you determined it. Size
of the work unit refers to the number of sub-problems that a worker gets
in a single request from the boss.

Answer : The size(or range) of the string(len) and k are our input parameter to a worker, who intends to mine bit coins.
Each worker(or actor) receives an input string length whihc defines his problem space.
for example, if an actor receives len=8 and k=3, he will generate random strings of length 8. 
We have 62 characters in our domain space.
Hence he has 62^8 problems to solve.
Since each worker will receive a different length, the subproblems between workers will not overlap. We found that 
the minimum size of work unit 8 to be efficient.

Each worker runs for 5 mins.


Question :
The result of running your program for
scala project1.scala 4

Answer:

 BigBoss has started
RemoteActor received message 'Namskara'
RemoteActor received message 'Hello I am a local miner 0. Can I start work?'
RemoteActor received message 'Hello I am a local miner 1. Can I start work?'
A Miner Completed its task
A Miner Completed its task
Total Bit Coins Found are 59
aholla;bfoFXfeC 00000b7417cca2540486a0607ef36ddc2bd4dde113bd69bba1e54fe3eac57765
aholla;zkWzLLfD 0000fd24de26fe9f6379f9d6bba79db6dbe2c5f561a9794778fb478ad0e71e8e
aholla;wOagms67 0000af87db2141e968420b137449601b2db2af4c1c21562a8a42edee4d618419
aholla;qqvTBaAi 0000f54d0f30e1d9212e28a97a5efc9f83a64bc4a896826ea115aa8d3066aaf7
aholla;YgRFGNFs 000087487a542fa8a96ee1baeb0063a7b64acca22083aa05226672ed8eb04632
aholla;og1I8Th0 000098e8824ca95f65a2f3a570eacd41468027ecd7d49497b455986e1dbfc563
aholla;v8Oh8kiI 0000fcc768997a80e8932fc8e2b22824e405af986b5913de0a89c63623098e72
aholla;XNClCvLA 000092647af4703675c0f0888752b040668ed1c5a75d0723fe85e05f7aad6533
aholla;oIoUNXzE 0000d0adedea87d8ebe2bdd2e1a91de103a88ae50f73695f063e90c341800db3
aholla;CqFMyEeb 000026c0cb3ff925793a756ae07d7fa948b01755f50e9074dc8400eda9dd9835
aholla;KdzEtZ4Q 00000317cf730e5c04fd9aa5c11495d41b53766183fc38cc680142ddf56f75e9
aholla;dBZxSxBm 0000629f9df177f65862bd3efd274b170c9694036ad72a2cfbffcc52707cec01
aholla;y264qqVO 00003db52337cf23dc5c71754aa08c02ad4533e5bc6e7f917cd82b4e53b70567
aholla;7KmWCeLS 0000d510fc1527175109c53bc255c5f7329a3351d7c79a5632c8168826625f85
aholla;ecuvLbdD 000086640a7965e32af9e9d17eb028a9922db4fa3199b65dc827f34d7a745847
aholla;Iw55WxqR 00000a21efd41096923c6366b2ead5301bcb4171882ac1fc21a54406e8b461b2
aholla;OEd4cNOK 000005dbbb578f815bdf0a76165ee2e367e73a3ce11647258e4bab6a5af6bd7c
aholla;OkTxqwvL 00009769c91c84cd0cfe84db5192e44d5ed168096ca990b93e82c3067d1ef845
aholla;DPxGRKre 00008db0686faf83f22b9acd97f701049fdf7154c5b36500c0166c837a1e2c51
aholla;6z3Xh3do 00006120d03222584c3d9ef1fdf512aea73bb2208fff1f83b9cc909eb67f0981
aholla;cfiAxm6X 00003074947c09664147ad56a9c30c28c2417d33f1191731821c09fb0c02fb8e
aholla;Nqglp1qa 0000d917dccab0eeed2129c354c9158c48763545435d6945a202c7c63f9d94c5
aholla;c9t4AYYZ 000084fbe644d147a143c54c5058e329736bb367306272f98843074f81c3cfbe
aholla;irNpLZv9 00003a0a4524dc8683e87b7f486c480796fa79f82d94ca1958aa2f53c332eabd
aholla;3fXzTQBH 00002e218fe4b46dd6669ade0ead5367a65fd6f594c814e9ee43d71541912028
aholla;OlLr2vFi 00002dafc3af148175f7c02c37656bffbe20da16cd5b375ceaa964e6ad974e1c
aholla;k9lxlYPC 0000f7396424bbf6d6be342cb193f0bcfb3615989316e618b582de48e09869f7
aholla;TZ2dEmaP 0000b0446f70faa6cbd39706663a305533ff27cd63ad044f8213be51e814fb7d
aholla;1I0GKOP8 00002da0a06a6aa6c115f153f17327ba04a55369016fc1499619fc3244538860
aholla;UwaCJ38o 0000b797cf7d827bab4ecea5e232012f0376cf38d29037ab099f1b184c73e779
aholla;gFsoCYYN 000086fc758a59597ad532ff84fcdd0c7e7d7ceae659c7aa680d967c4e44a782
aholla;nqbBohis 0000b11212476b81a108e59f610fecf22a50e2e36d07d5b16232e44470b6dc26
aholla;B77KCeu3 00000749e2be7627b49a5e5070666ec57027ecab2287e88a134b29f728239bb7
aholla;IaZX6Xu4 00005fd1acc2287d63e6fafd163d6fbb63403e7a066ee9fc9c632b829dee8ad4
aholla;xTTiMTEsR 0000c62107cdeef3d5e210863cc184cf5998c67863c358b0f504cf047c60707e
aholla;hxgwxIjEG 0000b665a089ae53561a4a77a1134d1ae1bb57976b3781ac84896a4bd184e4df
aholla;Sh6HsB00V 000083ae4340f9c5c7c753c2bc02422feaf9edbf5c83ddf65bf3df068e79be94
aholla;7G1e0kAuO 0000ce33b942d7213d5d70af6f364358edc7ba4a3465ed309709967a4ea6a5e2
aholla;E593rYV8l 000095a70218ead5a4283159414b5057e5cc7345c6440868b720a769b9f45ddc
aholla;SK88aEPgF 00008b9c876e6e4bcad96ecbdf3de086b503693a556cf73bfb3d68deda722b5b
aholla;GfT1VtftP 0000bbd3b1a66a670e38b8cee3657db4693b3c648f3c3d39861e1dc9bc93de9d
aholla;6z2cippZd 00003d571c81fa9db93693d659c682a9c5db3ce46831b8239669030a988e06dc
aholla;DBXxQFono 0000cba779f994bd8c6270d32968b81765721466e57ef6d00d632be3d11c2b92
aholla;G1idOeVTA 0000eb515ad94e875fd3541e1eb38eb9a03207965f0cb7f0ede198eb8bf6e349
aholla;MiTEpfwTd 00007ee96896b5ee576a2a1c45e30c061ea28f9cf7e5f6408973aac217e695cc
aholla;RAdxBKhfA 00003f0364c24b5ba7a9fed23bc8a8ac3968d563dc520d54e07ca0446b0719b6
aholla;PbwXRJYM1 0000d9dc3c774e9e8b6be314b8dad11be227d549be7e432177b76a5e731ebd92
aholla;p3pyMWBvC 0000738c034b6bd81d3fffdb3a81f9b0c4088d16dfc3463ff3e608dbb214b938
aholla;yATTXiP5e 0000701ed4521262834abdad99dc2948dc624b73034432f9d60c3d959491ae8f
aholla;shHg8zH8L 0000d9c6500f2f83d5df1c388bf2e5906325d869cde7425d920364a7668a617d
aholla;iDbqOMvyI 000020e23db7aa5c70ef9cb106d3c6bb46d95643d1ed4ee96b545a6a3d08b03a
aholla;MeYq49m17 0000cb44fecf8c7b73acc0c17bc3c3697acfe914efdd4261087bdbd03d1991a9
aholla;oM711eG51 0000cc24673de7bb97180571488a3be3de78cff2c7a8c2d0aa8418a9fc78cd46
aholla;nxZmsorgd 0000960b6d0f16f766ca267f9e7e4d85d86f0b6122be65a239efb7bb9c905e7d
aholla;8i0BiJJ4S 000007169bde140e5242fc079cb62d3e1af8af2b372db9f7f8c05292c68675bf
aholla;dQGCaK75X 000008180d22a3ded0750deea0bea58cf0127f1fd1c3b4d68782e1c505f39d06
aholla;OCxQ9qpVB 00001aedbaca251d54a04bc8956955bb4b1a817b5a68617a783a90c7b00876e6
aholla;CCqlMWiOo 00002fc289a5d8c4b641790918da9453ad9c7fd1e572c0ed7c59c5e0ecb7e3a4
aholla;JHRahnYF1 00001e769a18c701be2e3e30df38bfac24f6ece99227f2d329b77292cc6888c5
Total Bit Coins Found are 59 and 2 number of miners were involved

Question : The running time for the above as reported by time for the above, i.e. run
time scala project1.scala 5 and report the time. The ratio of CPU
time to REAL TIME tells you how many cores were eectively used in
the computation. If your are close to 1 you have almost no parallelism
(points will be subtracted).

Answer :

real    5m1.257s
user    0m15.064s
sys     3m40.728s

ratio : 0.6

**
Question : The coin with the most 0s you managed to nd.
Answer :
5   aholla;WTAnhR1D3fv3 00000f9774ca55067bd9cc9dfae7b7ab2de1fab44173b0e49c6eb4af8c54c7bb

Question :The largest number of working machines you were able to run your code
with.

Answer : 4
