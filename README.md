# MCP Python SDK Example

## 試したところ

transportTypeはstdioにしてます。

* 参考をもとに、server.pyにmcp.runを追加
* uv run server.pyを実行したまま
* cline_mcp_settings.jsonを設定
* その後task上で python-mcp-example-stdio を認識できるかとか聞くと使い方を教えてくれる。
* 実行例
  * add 1 2 と入れる -> 実行確認が出てくるから、Approveすると結果を返してくれる
  * 自然言語でやりたいことを言うと自動的にadd toolを使ってくれる

    ```text
    では addツールを使って、 4つの数字を合計して
    10, 20, 30, 40
    ```

## cline_mcp_settings.jsonの例

commandのuvはフルパスがいいっぽいです。ここでは`/opt/homebrew/bin/uv`にしています。

```json
{
  "mcpServers": {
    "python-mcp-example-stdio": {
      "disabled": false,
      "timeout": 60,
      "command": "/opt/homebrew/bin/uv", 
      "args": [
        "--directory",
        "/path/to/server.py/",
        "run",
        "server.py"
      ],
      "transportType": "stdio"
    }
  }
}
```

## まだわかってない/やっていないこと

* SSEの使い方
* MCP Inspectorの使い方
* 外部のAPIを使う

## 参考

[MCP Python SDK を使って、echoするだけのMCPサーバを作ってみた - メモ的な思考的な](https://thinkami.hatenablog.com/entry/2025/04/01/000255#MCP%E3%82%B5%E3%83%BC%E3%83%90%E3%82%92%E4%BD%9C%E3%82%8B)
