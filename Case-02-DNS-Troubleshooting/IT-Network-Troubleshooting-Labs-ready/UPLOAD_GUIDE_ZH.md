# GitHub 上传说明（中文版）

这个压缩包已经包含：
- 仓库首页 `README.md`
- 案例报告 `Case-02-DNS-Troubleshooting/README.md`
- 你提供的 4 张原始 Packet Tracer 截图（没有篡改命令输出）

## 上传步骤

1. 在 Mac 上解压 ZIP。
2. 如果还没有 GitHub 仓库：打开 https://github.com/new ，命名为 `IT-Network-Troubleshooting-Labs`，设为 Public（只有确认内容没问题再公开），不要初始化自动 README。
3. 仓库空页面点击 `uploading an existing file`；有文件的仓库点击 `Add file → Upload files`。
4. 将解压后 `IT-Network-Troubleshooting-Labs-ready` 文件夹**内部**的 `README.md` 和 `Case-02-DNS-Troubleshooting` 文件夹一起拖入上传区域，保留目录结构。
5. 填写提交消息：`Add DNS troubleshooting lab with screenshots`，点击 Commit changes。
6. 打开案例 README，确认四张图片都显示出来。

## 更完整的证据（建议在公开展示前补充）

- 在 Server0 → Services → DNS 将服务改回 On，截取 `DNS Service: On` 的图片；
- 在 Laptop0 → Desktop → Command Prompt 重新执行 `ping intranet.firma.test`，保存其成功输出；
- 在 Packet Tracer 中保存真实 `.pkt` 项目文件，命名 `02-DNS-Failure.pkt` 和 `02-DNS-Recovered.pkt`，上传到案例目录。

**注意**：截图中的第一次命令将 `ping` 和 `nslookup` 粘在一起而报错。文档没有把它冒充为 DNS 查询测试；只记录下面正确执行的两个 ping 命令。

**注意**：浏览器截图证明域名访问正常，但没有拍到 DNS 服务重新开启的设置，因此文档明确标注了这一证据限制。

不要上传真实公司的账号、IP、密码或内部网络配置；本案例使用的是模拟环境地址。
