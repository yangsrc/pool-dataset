# Introduction

The data set in our paper **Characterizing Ethereum's Mining Power Decentralization at a Deeper Level(Accepted by [INFOCOM 2021](https://infocom2021.ieee-infocom.org/accepted-paper-list-main-conference))** is available here.

In Ethereum's Proof-of-Work(POW) consensus protocol, mining pools and solo miners receive <b>rewards(ethers)</b> from the system, and pools distribute the rewards to pool participants based on their relative mining power contribution. 

We collect all reward payments to mining pools and participants in the first  9,847,646 blocks of Ethereum, from July 30, 2015 through April 10, 2020.  

The data set consists of four major parts: 1)all reward payments received by mining pools and solo miners from the protocol,  named as <b>mining rewards</b>. 2)  all reward payments received by pool participants from mining pools, named as <b>pool rewards</b>. 3) mining pools' accounts identified from [Etherscan](<https://etherscan.io/stat/miner?range=7&blocktype=blocks>). 4) pool participants' accounts verified through mining pool APIs.

Here are related files you can download freely:

<b>[mining_reward_payment.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/mining_reward_payment.csv?sp=r&st=2019-10-13T11:35:15Z&se=2020-10-29T19:35:15Z&spr=https&sv=2018-03-28&sig=HrIayuWJBA4%2F6MNgYHBSoP7fkYfu1zie5fdJZ8aIodQ%3D&sr=b)</b>

|                  Address                   |     Value(Wei)      | BlockNumber | Timestamp  | RewardType  |
| :----------------------------------------: | :-----------------: | :---------: | :--------: | :---------: |
| 0x829bd824b016326a401d083b33d092293333a830 | 2000000000000000000 |   9623276   | 1583571588 | MinerReward |
| 0x52bc44d5378309ee2abf1539bf71de1b7d7be3b5 | 1750000000000000000 |   9623277   | 1583571622 | UncleReward |

It contains all mining reward payments received by mining pools and solo miners from the system.

The <b>Address</b> represents the account which belongs to a mining pool or a solo miner.

The <b>Value</b> shows how much reward the account receives(1 ETH = 10^18 Wei ).

The <b>BlockNumber</b> and <b>Timestamp</b> show in which block and when the payment is packaged.

The <b>RewardType</b> consists of two kinds, including <b>MinerReward</b> and <b>UncleReward</b>.

Here are **5,447** distinct accounts.

Here are **9,847,646** MinerReward payments and **1,004,359** UncleReward payments.

--

<b>[recognized_pool_info.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/recognized_pool_info.csv?sp=r&st=2021-01-13T06:52:16Z&se=2024-01-01T14:52:16Z&spr=https&sv=2019-12-12&sr=b&sig=de%2Fg5MxwyIg61qPutoJZpJHkoG4miNVgm5kikduDxpg%3D)</b>

|  ID  |                  Address                   | PoolName  |
| :--: | :----------------------------------------: | :-------: |
|  22  | 0x4bb96091ee9d802ed039c4d1a5f6216f90f81b01 |  EthPool  |
|  23  | 0xe6a7a1d47ff21b6321162aea7c6cb457d5476bca |  EthPool  |
|  0   | 0xea674fdde714fd979de3edf0f56aa9716b898ec8 | Ethermine |

It contains accounts which we identify as mining pools from Etherscan.

Some pools have multiple accounts, like Ethpool.

Each account has a unique **ID**(0~66).

Here are **47** distinct mining pools and **67** related accounts.

--

<b>[recognized_participant_info.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/recognized_participant_info.csv?sp=r&st=2021-01-13T08:38:17Z&se=2023-12-31T16:38:17Z&spr=https&sv=2019-12-12&sr=b&sig=F0ACAISkVYbcw1Uas%2Bz2iNGxkIvRxLqdXcStVc7Gatc%3D)</b>

|  ID   |                  Address                   |     PoolName     |
| :---: | :----------------------------------------: | :--------------: |
| 31746 | 0x1c139f20557a682a4b1baedc1850ded9af3d2463 |    Ethermine     |
| 31750 | 0xd23d5580390f41a1a9cda331a64ca049e0c51c8e | EthPool/NanoPool |

It contains all participant accounts verified through the mining pool APIs.

Each account has a unique <b>ID</b>(0~980167).

The <b>PoolName</b> shows by which pool APIs the participant account is recognized. Some participants are recognized by more than one pools.

Here are **980,168** distinct participant accounts.

--

<b>[pool_reward_payment.csv](https://miningpaper.blob.core.windows.net/data-sharing-2/pool_reward_payment.csv?sp=r&st=2019-10-15T08:05:25Z&se=2020-10-29T16:05:25Z&spr=https&sv=2018-03-28&sig=ih3E2aeItJ%2BSq29D2n2L2H8G%2FeAtar4sV%2BPtFTwbUa0%3D&sr=b)</b>

| PoolID | ParticipantID |     Value(Wei)     | BlockNumber | Timestamp  |
| :----: | :-----------: | :----------------: | :---------: | :--------: |
|   4    |    170043     | 118093644687491078 |   6103615   | 1533631607 |
|   29   |    594033     | 143869621000000000 |   6042297   | 1532738690 |

It contains all pool reward payments from the identified 47 mining pools to the verified participants.

The <b>PoolID</b> represents the pool account in the *recognized_pool_info.csv* .

The <b>ParticipantID</b> represents the participant account in the *recognized_participant_info.csv*.

The <b>Value</b> shows how much reward is received by the participant from the pool.

The <b>BlockNumber</b> and <b>Timestamp</b> show in which block and when the payment is packaged.

Here are **62,358,646** pool reward payments.













