### 如何在 BSC 上用智能合约发币

简单把各个链接和流程浓缩在这里：

1. Metamask 钱包地址

Chrome 应用商城自行搜索，安装好后创建自己的地址，并保存好私钥。

2. 切换至 BSC Testnet:

a. 网络名称：BSC Testnet

b. RPC URL: https://speedy-nodes-nyc.moralis.io/03a2a57cae4f839aae2eb484/bsc/testnet

c. 链 ID: 97

d. 代币符号: BNB

e. 区块浏览器 URL: https://testnet.bscscan.com/

3. 获取免费的一个 BNB，注意每 24 小时只能领取一次

https://testnet.binance.org/faucet-smart

4. ERC20 的详细解释

https://eips.ethereum.org/EIPS/eip-20

5.代码编辑器（IDE)

https://remix.ethereum.org/

打开后创建一个名为 Token.sol 的文件

6. 完整代码，注意版本请使用^0.8.0

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token//ERC20/ERC20.sol";

contract Token is ERC20 {
// 这里把 Your name 改成你想要的代币名称，如 Bitcoin, Litecoin, Dogecoin
// 如 string public token_name = "Bitcoin";
string public token_name = "Your name";
// 这里把 Your ticker 改成你想要的代笔简写，如 BTC，LTC, DOGE
// 如 string public token_ticker = "BTC";
string public token_ticker = "Your ticker";

    constructor () ERC20(token_name, token_ticker) {
        _mint(msg.sender, 1000000 * (10 ** uint256(decimals())));
    }

} 7. compiler, deploy...

8.在 bscscan 中找到对应的合约地址，并在 Metamask 中添加代币
