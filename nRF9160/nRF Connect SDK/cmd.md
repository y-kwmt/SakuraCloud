※以下はあくまで個人的な調査結果なので非公式な内容となります.

# 定数定義

|名称   |CMD_BUFF_SZ 4096                   |
|---    |---                                |
|説明   |入力バッファ/出力バッファのサイズ. |

# 列挙体定義

|名称                       |CmdState                                   |
|---                        |---                                        |
|CMD_STATE_WAIT             |コマンドの先頭文字('$')待ち.               |
|CMD_STATE_BUFFERING_ASCII  |コマンド入力中.入力完了時にコマンドを実行. |
|CMD_STATE_BUFFERING_BIN    |未使用.                                    |
|_CMD_STATE_CNT_            |未使用.                                    |

# 構造体定義

|名称                   |CmdResponse                |
|---                    |---                        |
|uint8_t *response      |実行結果の先頭アドレス.    |
|uint16_t response_len  |実行結果のデータサイズ.    |
|説明                   |コマンドの実行結果.        |

# 外部API

|名称   |CmdResponse *CmdParse(uint8_t b)                       |
|---    |---                                                    |
|戻り値 |NULL : コマンド実行なし NULL以外 : コマンドの実行結果. |
|引数   |uint8_t b : 入力値.                                    |
|説明   |モジュールの状態に応じた処理を呼び出す.                |
