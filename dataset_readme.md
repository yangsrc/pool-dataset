# Introduction

The data set in our paper is available here.

In Ethereum's Proof-of-Work(POW) consensus protocol, mining pools and solo miners receive <b>rewards(ethers)</b> from the system, and pools distribute the rewards to pool participants based on their relative mining power contribution. 

We collect all reward payments to mining pools and participants in the first 7,500,000 blocks of Ethereum, from July 30, 2015 to April 4, 2019.  

The data set consists of four major parts: 1)all reward payments received by mining pools and solo miners from the protocol,  named as "<b>mining rewards</b>". 2)  all reward payments received by pool participants from mining pools, named as "<b>pool rewards</b>". 3) mining pools' accounts identified from [Etherscan](<https://etherscan.io/stat/miner?range=7&blocktype=blocks>). 4) pool participants' accounts verified through mining pool APIs.

Here are related files you can download freely:

<b>[mining_reward_receiver_account.csv](https://miningpaper.blob.core.windows.net/data-sharing/mining_reward_receiver_account.csv?sp=r&st=2019-05-22T09:59:34Z&se=2025-05-21T17:59:34Z&spr=https&sv=2018-03-28&sig=0y28MZ7ZuqJK%2FUFHn05AfUcz%2FCMlRT%2BGfKoRA%2FnSXOM%3D&sr=b)</b>

|  id  |                  address                   |
| :--: | :----------------------------------------: |
|  0   | 0x2635552e5587ab6c7ff340d0422debe13115a866 |
|  1   | 0x6e4f44d118e5294ee3e838259ba7e8b0290242d3 |

It contains all accounts which receive mining rewards from the system, representing mining pools or solo miners.

Each account has a unique <b>id</b>.

Here are 4,968 distinct accounts.

--

<b>[recognized_pool_info.csv](https://miningpaper.blob.core.windows.net/data-sharing/recognized_pool_info.csv?sp=r&st=2019-05-22T10:04:12Z&se=2025-05-21T18:04:12Z&spr=https&sv=2018-03-28&sig=Vw%2Fz%2FJYKNO1ypLpaezUJjFRS%2FiVc5SCVJvN%2FxiRW0jw%3D&sr=b)</b>

|  id  |                  address                   |   name    |
| :--: | :----------------------------------------: | :-------: |
| 2185 | 0x4bb96091ee9d802ed039c4d1a5f6216f90f81b01 |  Ethpool  |
| 673  | 0xe6a7a1d47ff21b6321162aea7c6cb457d5476bca |  Ethpool  |
| 1343 | 0xea674fdde714fd979de3edf0f56aa9716b898ec8 | Ethermine |

It contains accounts which we identify as mining pools from Etherscan.

Some pools have multiple accounts, like Ethpool.

The same <b>id</b> here and in the *mining_reward_receiver_account.csv* represents the same account.

Here are 40 distinct mining pools and 56 related accounts.

--

<b>[mining_reward_payment.csv](https://miningpaper.blob.core.windows.net/data-sharing/mining_reward_payment.csv?sp=r&st=2019-05-22T09:54:44Z&se=2025-05-21T17:54:44Z&spr=https&sv=2018-03-28&sig=K6gfVLKZ2Zo5AtKMGadHEreWGi5lgOt7VWORGRg56VE%3D&sr=b)</b>

|  id  |     value(Wei)      | block_number | timestamp  | reward_type |
| :--: | :-----------------: | :----------: | :--------: | :---------: |
| 2185 | 5000000000000000000 |   2970900    | 1484060380 | MinerReward |
| 1343 | 3750000000000000000 |   2970919    | 1484060723 | UncleReward |

It contains all mining reward payments.

The <b>id</b> represents the account in the *mining_reward_receiver_account.csv*.

The <b>value</b> shows how much reward the account receives(1 ETH = 10^18 Wei ).

The <b>block_number</b> and <b>timestamp</b> show which block and when the payment is packaged in.

The <b>reward_type</b> consists of two kinds, including <b>MinerReward</b> and <b>UncleReward</b>.

Here are 7,500,000 MinerReward payments and 852,866 UncleReward payments.

--

<b>[recognized_participant_info.csv](https://miningpaper.blob.core.windows.net/data-sharing/recognized_participant_info.csv?sp=r&st=2019-05-22T10:03:01Z&se=2025-05-21T18:03:01Z&spr=https&sv=2018-03-28&sig=Slta1HFjKFEpQVAZhbDCtgCWbNoM9De1Nb7VJsO50MU%3D&sr=b)</b>

|  id  |                  address                   |        pool        |
| :--: | :----------------------------------------: | :----------------: |
|  0   | 0x8cf7b19255ad265ec318b1f115a28f25ffd74ce4 | Nanopool/Ethermine |
|  3   | 0x3a1f509fd8dc7d9de9853e7eaa5f0524bbe365cd |     Ethermine      |

It contains all participant accounts verified through the mining pool APIs.

Each account has a unique <b>id</b>.

The <b>pool</b> shows one or more pools whose APIs recognize the account as participant account.

Here are 921,795 distinct participant accounts.

--

<b>[pool_reward_payment.csv](https://miningpaper.blob.core.windows.net/data-sharing/pool_reward_payment.csv?sp=r&st=2019-05-22T10:01:13Z&se=2025-05-21T18:01:13Z&spr=https&sv=2018-03-28&sig=e7Jb9PCk6LVSBrbIOq1XE3ieY%2B9QzONiCconL78c7i0%3D&sr=b)</b>

| pool_id | participant_id | value(Wei)          | block_number | timestamp  |
| ------- | -------------- | ------------------- | ------------ | ---------- |
| 150     | 732369         | 157479170000000000  | 3332703      | 1489242003 |
| 1343    | 408524         | 2008559493396762600 | 3332707      | 1489242099 |

It contains all pool reward payments from the identified 40 mining pools to the verified participants.

The <b>pool_id</b> represents the pool account in the *recognized_pool_info.csv* .

The <b>participant_id</b> represents the participant account in the *recognized_participant_info.csv*.

The <b>value</b> shows how much reward is received by the participant from the pool.

The <b>block_number</b> and <b>timestamp</b> show which block and when the payment is packaged in.

Here are 49,489,711 pool reward payments.













