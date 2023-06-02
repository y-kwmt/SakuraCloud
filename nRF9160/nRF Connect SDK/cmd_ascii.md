※以下はあくまで個人的な調査結果なので非公式な内容となります.

# 定数定義

|名称   |CMD_REG_W "W"              |
|---    |---                        |
|説明   |レジスタ書込みコマンド.    |

|名称   |CMD_REG_R "R"              |
|---    |---                        |
|説明   |レジスタ読込みコマンド.    |

|名称   |CMD_TX "$TX"               |
|---    |---                        |
|説明   |オブジェクト送信コマンド.  |

|名称   |CMD_RX "$RX"               |
|---    |---                        |
|説明   |オブジェクト受信コマンド.  |

|名称   |CMD_TXRAW "$TXRAW"             |
|---    |---                            |
|説明   |公式資料にない為、詳細不明.    |

|名称   |CMD_FPUT "$FPUT"       |
|---    |---                    |
|説明   |ファイル送信コマンド.  |

|名称   |CMD_FGET "$FGET"       |
|---    |---                    |
|説明   |ファイル受信コマンド.  |

|名称   |CMD_UNLOCK "$UNLOCK"                       |
|---    |---                                        |
|説明   |管理コマンドのロックを解除するコマンド.    |

|名称   |CMD_UPDATE "$UPDATE"           |
|---    |---                            |
|説明   |SIPF Firmwareの更新コマンド.   |

|名称   |CMD_GNSS_ENABLE "$GNSSEN"      |
|---    |---                            |
|説明   |公式資料にない為、詳細不明.    |

|名称   |CMD_GNSS_GET_STATUS "$GNSSSTAT"    |
|---    |---                                |
|説明   |公式資料にない為、詳細不明.        |

|名称   |CMD_GNSS_GET_LOCATION "$GNSSLOC"   |
|---    |---                                |
|説明   |公式資料にない為、詳細不明.        |

|名称   |CMD_GNSS_GET_NMEA "$GNSSNMEA"  |
|---    |---                            |
|説明   |公式資料にない為、詳細不明.    |

|名称   |CMD_RES_OK (0)         |
|---    |---                    |
|説明   |詳細不明.              |

|名称   |CMD_RES_ILLPARM (-1)   |
|---    |---                    |
|説明   |詳細不明.              |

|名称   |CMD_RES_CMDFAIL (-2)   |
|---    |---                    |
|説明   |詳細不明.              |

|名称   |CMD_RES_LOCKED (-3)    |
|---    |---                    |
|説明   |詳細不明.              |

# 外部API

|名称   |int CmdAsciiParse(uint8_t *in_buff, uint16_t in_buff_len, uint8_t *out_buff, uint16_t out_buff_len)|
|---    |---                                                                                                |
|戻り値 |出力データのサイズ.                                                                                |
|引数   |uint8_t *in_buff : 入力データ.                                                                     |
|引数   |uint16_t in_buff_len : 入力データのサイズ.                                                         |
|引数   |uint8_t *out_buff : 出力データの先頭アドレス.                                                      |
|引数   |uint16_t out_buff_len : 出力データのバッファサイズ.                                                |
|説明   |入力データに基づいてコマンド処理を実行する.                                                        |
