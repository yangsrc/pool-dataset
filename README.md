# Introduction

The data set in our paper **Characterizing Ethereum's Mining Power Decentralization at a Deeper Level(Accepted by [INFOCOM 2021](https://infocom2021.ieee-infocom.org/accepted-paper-list-main-conference))** is available here.

In Ethereum's Proof-of-Work(POW) consensus protocol, mining pools and solo miners receive <b>rewards(ethers)</b> from the system, and pools distribute the rewards to pool participants based on their relative mining power contribution. 

We collect all reward payments to mining pools and participants in the first  9,847,646 blocks of Ethereum, from July 30, 2015 through April 10, 2020.  

The data set consists of four major parts: 1)all reward payments received by mining pools and solo miners from the protocol,  named as <b>mining rewards</b>. 2)  all reward payments received by pool participants from mining pools, named as <b>pool rewards</b>. 3) mining pools' accounts identified from [Etherscan](<https://etherscan.io/stat/miner?range=7&blocktype=blocks>). 4) pool participants' accounts verified through mining pool APIs.

Here are related files you can download freely:

<div id="1" ><b>[mining_reward_receiver_account.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/mining_reward_receiver.csv?sp=r&st=2019-10-13T10:58:33Z&se=2020-10-29T18:58:33Z&spr=https&sv=2018-03-28&sig=7PwS9AjTLGdzmbupVsmrkgnDt7Ss0Cr60xI%2BDnfO7Y8%3D&sr=b)</b></div>

|  id  |                  address                   |
| :--: | :----------------------------------------: |
|  0   | 0x6f8fc6d5d9df81850261f3859cf8c52d69bc6dca |
|  1   | 0xe160bb81383a5c4a562088d90f49e0f4b4bc6d1e |

It contains all accounts which receive mining rewards from the system, representing mining pools or solo miners.

Each account has a unique <b>id</b>.

Here are 5,447 distinct accounts, which receive block/uncle rewards.

--

<b>[recognized_pool_info.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/mining_pool.csv?sp=r&st=2019-10-13T11:19:48Z&se=2020-10-29T19:19:48Z&spr=https&sv=2018-03-28&sig=oQ1IwjiML2NvAnIyvWaxUDum3SrZI796lsuOFyfVIgg%3D&sr=b)</b>

|  id  |                  address                   |   name    |
| :--: | :----------------------------------------: | :-------: |
| 366  | 0x4bb96091ee9d802ed039c4d1a5f6216f90f81b01 |  Ethpool  |
| 1197 | 0xe6a7a1d47ff21b6321162aea7c6cb457d5476bca |  Ethpool  |
| 1509 | 0xea674fdde714fd979de3edf0f56aa9716b898ec8 | Ethermine |

It contains accounts which we identify as mining pools from Etherscan.

Some pools have multiple accounts, like Ethpool.

The same <b>id</b> here and that in the *[mining_reward_receiver_account.csv](#1)* represents the same account.

Here are 47 distinct mining pools and 67 related accounts.

--

<b>[mining_reward_payment.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/mining_reward_payment.csv?sp=r&st=2019-10-13T11:35:15Z&se=2020-10-29T19:35:15Z&spr=https&sv=2018-03-28&sig=HrIayuWJBA4%2F6MNgYHBSoP7fkYfu1zie5fdJZ8aIodQ%3D&sr=b)</b>

|  id  |     value(Wei)      | block_number | timestamp  | reward_type |
| :--: | :-----------------: | :----------: | :--------: | :---------: |
| 1524 | 5000000000000000000 |    60001     | 1439147254 | MinerReward |
| 4168 | 3750000000000000000 |    60003     | 1439147361 | UncleReward |

It contains all mining reward payments.

The <b>id</b> represents the account in the *mining_reward_receiver_account.csv*.

The <b>value</b> shows how much reward the account receives(1 ETH = 10^18 Wei ).

The <b>block_number</b> and <b>timestamp</b> show which block and when the payment is packaged in.

The <b>reward_type</b> consists of two kinds, including <b>MinerReward</b> and <b>UncleReward</b>.

Here are 9,847,646 MinerReward payments and 1,004,359 UncleReward payments.

--

<b>[recognized_participant_info.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/identified_participant.csv?sp=r&st=2019-10-13T11:36:17Z&se=2020-10-29T19:36:17Z&spr=https&sv=2018-03-28&sig=lkgA2rF1DrjRA86B4IXFDXOy2iY7SNfmUEdMZ4sAZtQ%3D&sr=b)</b>

|  id  |                  address                   |       pool       |
| :--: | :----------------------------------------: | :--------------: |
|  0   | 0xa2adbcac67e3a0dbba49b0cd3dd216ee9702e64b |    Ethermine     |
|  1   | 0x9d0b51b932d20787eaeea27ae251ff448a97f692 | SparkPool/F2Pool |

It contains all participant accounts verified through the mining pool APIs.

Each account has a unique <b>id</b>.

The <b>pool</b> shows one or more pools whose APIs recognize the account as participant account.

Here are 980,168 distinct participant accounts.

--

<b>[pool_reward_payment.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/pool_reward_payment.csv?sp=r&st=2019-10-15T08:05:25Z&se=2020-10-29T16:05:25Z&spr=https&sv=2018-03-28&sig=ih3E2aeItJ%2BSq29D2n2L2H8G%2FeAtar4sV%2BPtFTwbUa0%3D&sr=b)</b>

| pool_id | participant_id | value(Wei)          | block_number | timestamp  |
| ------- | -------------- | ------------------- | ------------ | ---------- |
| 4345    | 820941         | 132160792774361000  | 4130622      | 1502164246 |
| 677     | 909983         | 1030838540000000000 | 6910503      | 1545158215 |

It contains all pool reward payments from the identified 47 mining pools to the verified participants.

The <b>pool_id</b> represents the pool account in the *recognized_pool_info.csv* .

The <b>participant_id</b> represents the participant account in the *recognized_participant_info.csv*.

The <b>value</b> shows how much reward is received by the participant from the pool.

The <b>block_number</b> and <b>timestamp</b> show which block and when the payment is packaged in.

Here are 62,358,646 pool reward payments.













