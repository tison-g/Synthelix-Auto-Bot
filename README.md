# Synthelix 自动机器人

**用于管理多个钱包中的 Synthelix 节点的自动化工具**

## 🌟 功能特性

- 👛 通过单个脚本管理多个以太坊钱包
- 🚀 自动启动节点以实现最大在线时间
- 💎 自动领取每日奖励
- 📊 监控节点状态、运行时间和积分
- 🔄 需要时自动重启节点
- 🌐 支持代理，实现更好的稳定性和多账户管理
- 🏃‍♂️ 运行即可，支持自动监控

## 📋 前置要求

- Node.js (v14+)
- NPM 或 Yarn
- 以太坊钱包私钥
- 可选：管理多账户的代理列表

## 🚀 安装步骤

1. 克隆仓库：
```bash
git clone https://github.com/airdropinsiders/Synthelix-Auto-Bot.git
cd Synthelix-Auto-Bot
```

2. 安装依赖：
```bash
npm install
```

3. 设置环境：
```bash
cp .env.example .env
```

4. 编辑 `.env` 文件，填入您的私钥：
```
# 单个钱包
PRIVATE_KEY=你的私钥

# 多个钱包（用逗号分隔）
PRIVATE_KEY=私钥1,私钥2,私钥3

# 或者多个钱包（编号）
PRIVATE_KEY_1=私钥1
PRIVATE_KEY_2=私钥2
PRIVATE_KEY_3=私钥3
```

5. （可选）设置代理：
   - 创建名为 `proxies.txt` 的文件
   - 每行添加一个代理，支持以下格式：
     ```
     http://用户名:密码@主机:端口
     socks5://用户名:密码@主机:端口
     主机:端口
     ```

## 🏃‍♂️ 使用方法

启动机器人：
```bash
npm start
```

机器人将：
1. 依次登录每个钱包
2. 如果节点未运行则启动节点
3. 如果有可用的每日奖励则领取
4. 监控并在需要时重启节点
5. 显示状态信息和获得的积分

## ⚙️ 配置

在 `index.js` 中编辑以下常量来调整行为：

```javascript
const DELAY_BETWEEN_WALLETS = 2000; // 钱包操作之间的延迟（毫秒）
const MAX_RETRIES = 3;              // 最大登录重试次数
const CHECK_INTERVAL = 60 * 1000;   // 状态检查间隔（毫秒）
```

## 📝 日志

机器人提供彩色控制台输出，显示：
- 钱包连接状态
- 节点操作（启动/停止）
- 获得的积分
- 错误信息
- 汇总统计

## 🔒 安全性

- 您的私钥存储在本地的 `.env` 文件中
- 切勿分享您的 `.env` 文件或私钥
- 建议使用具有有限资金的专用钱包以增加安全性

## 📄 许可证

本项目采用 MIT 许可证 - 详见 LICENSE 文件。

## 🤝 贡献

欢迎贡献、问题反馈和功能请求！

## ⚠️ 免责声明

本工具仅供教育目的使用。使用风险自负。本工具的创建者对使用过程中可能出现的任何潜在损失或问题概不负责。

## 💬 支持

加入我们的社区：
- [Discord](https://discord.gg/tmrBhAxU)
- [Telegram](https://t.me/AirdropInsiderID)
