※以下はあくまで個人的な調査結果なので非公式な内容となります.  

# 定数定義

|名称   |UART_LABEL DT_NODELABEL(uart0)                 |
|---    |---                                            |
|説明   |詳細不明. nRF9160でUARTを使用するための定義.   |

|名称   |UART_TX_BUF_SZ (256)                       |
|---    |---                                        |
|説明   |toolchainにわたす送信用バッファのサイズ.   |

|名称   |UART_RX_BUF_SZ (256)                       |
|---    |---                                        |
|説明   |toolchainにわたす送信用バッファのサイズ.   |

# 外部API

|名称   |int UartBrokerInit(const struct device *uart)  |
|---    |---                                            |
|戻り値 |0固定.                                         |
|引数   |スレッド作成時に使用するパラメータ.            |
|説明   |モジュールの初期化処理.                        |

|名称   |int UartBrokerTerm(void)   |
|---    |---                        |
|戻り値 |0固定.                     |
|引数   |なし.                      |
|説明   |処理なし.                  |

|名称   |bool UartBrokerSetEcho(bool echo)  |
|---    |---                                |
|戻り値 |引数echoの値.                      |
|引数   |bool echo : true あり false なし   |
|説明   |ECHO BACKの有無を切り替える.       |


|名称   |int UartBrokerPutByte(uint8_t byte)                                                                    |
|---    |---                                                                                                    |
|戻り値 |0 Message sent. -ENOMSG Returned without waiting or queue purged. -EAGAIN Waiting period timed out.    |
|引数   |uint8_t byte : 出力する文字.                                                                           |
|説明   |メッセージキューに送信データを設定する.                                                                |

|名称   |int UartBrokerPut(uint8_t *data, int len)  |
|---    |---                                        |
|戻り値 |送信したデータのサイズ.                    |
|引数   |uint8_t *data : 送信データ.                |
|引数   |int len : 送信データのサイズ.              |
|説明   |メッセージキューに送信データを設定する.    |

|名称   |int UartBrokerGetByte(uint8_t *byte)                                                       |
|---    |---                                                                                        |
|戻り値 |0 Message received. -ENOMSG Returned without waiting. -EAGAIN Waiting period timed out.    |
|引数   |uint8_t *byte : 受信データの出力先アドレス.                                                |
|説明   |メッセージキューから受信データを取得する.                                                  |

|名称   |int UartBrokerGetByteTm(uint8_t *byte, int timeout_ms)                                     |
|---    |---                                                                                        |
|戻り値 |0 Message received. -ENOMSG Returned without waiting. -EAGAIN Waiting period timed out.    |
|引数   |uint8_t *byte : 受信データの出力先アドレス.                                                |
|引数   |int timeout_ms : タイムアウト時間[ms].                                                     |
|説明   |メッセージキューから受信データを取得する.                                                  |


|名称   |int UartBrokerGet(uint8_t *data, int len)                                  |
|---    |---                                                                        |
|戻り値 |受信したデータのサイズ.                                                    |
|引数   |uint8_t *data : 受信データの出力先アドレス.                                |
|引数   |int len : 受信するデータのサイズ.                                          |
|説明   |受信するデータのサイズを指定してメッセージキューから受信データを取得する.  |

|名称   |int UartBrokerPuts(const char *msg)    |
|---    |---                                    |
|戻り値 |送信した文字列のサイズ.                |
|引数   |uint8_t *data : 文字列.                |
|説明   |メッセージキューに文字列を設定する.    |

|名称   |void UartBrokerClearRecveiveQueue(void)                                |
|---    |---                                                                    |
|戻り値 |なし                                                                   |
|引数   |なし                                                                   |
|説明   |メッセージキューをパージする. 受信バッファ内のメッセージを破棄する.    |

# マクロ定義

|名称   |UartBrokerPrint                                |
|---    |---                                            |
|引数   |... : 結合してUART出力する文字列               |
|説明   |引数に設定した文字列を結合してUART出力する.    |
