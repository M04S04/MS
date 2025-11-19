MS — IQデータ処理ツール （I/Qトリム・リサンプリング・スペクトラム表示）

このリポジトリには、I/Qデータを処理するための Jupyter Notebook resample_IQ.ipynb が含まれています。

✔ できること I/Q ファイルの読み込み（自動フォーマット判定） int16 I/Q 交互 (.bin, .dat, .iq など) complex .npy WAV ステレオ（L=I, R=Q） トリミング（開始〜終了時間またはサンプル数で切り出し） リサンプリング（polyphase） 入力フォーマットを保持したまま出力 WAV の場合はヘッダの Fs を優先 スペクトラム表示 NFFT サイズ、ウィンドウ、中心周波数指定 Fs が不明な場合は正規化周波数で描画

✔ 必要環境 Python 3.10+ numpy scipy matplotlib ipywidgets Jupyter Lab

✔ 使い方

Jupyter Lab を起動
resample_IQ.ipynb を開く
UI を使って I/Q データを処理する ▶ (1) I/Qファイルの読み込み Notebook 上部のファイル選択ドロップダウンから .wav, .bin, .dat, .iq, .npy のいずれかを選ぶ。 フォーマットは 自動判定 されます。 ▶ (2) “Analyze” ボタンで解析 フォーマット自動判定の結果を表示 WAV の場合はヘッダの Fs を表示 入力サンプル数や録音時間の情報を表示 ▶ (3) トリミング（任意） サンプル番号 または 秒指定（Start time / End time） どちらを優先するかは、Notebook のUIで選択できます。 ▶ (4) リサンプリング Input Fs（MHz） → WAV の場合はヘッダが優先 Output Fs（MHz） → 任意の帯域へ変換可能 Recenter（中心周波数移動）も可能 ▶ (5) 保存 処理後は入力フォーマットに合わせて自動保存されます。 例： sample_Fs2p000000MHz.wav
✔ 注意事項 WAV は ステレオ（L=I, R=Q） を想定 WAV のヘッダがある場合、 ユーザー入力の Fs よりヘッダを優先 します Fs が不明なデータは 正規化周波数 でスペクトラムを描画 周波数軸は複素ベースバンド（−Fs/2 ～ +Fs/2）で表示

MS
Tools for IQ data processing (resample / trim / spectrum viewer).

This repository contains a Jupyter notebook (resample_IQ.ipynb) that provides:

I/Q file trimming
Resampling (polyphase, preserves original format)
Spectrum viewer (auto format detection)
WAV header-aware processing (Fs from header is used if present)
Requirements
Python 3.10+
numpy
scipy
matplotlib
ipywidgets
Jupyter Lab
Usage
Launch Jupyter Lab:
Open resample_IQ.ipynb.
Run all cells.
Use the UI widgets to:
Load I/Q files (.bin, .dat, .iq, .npy, .wav)
Analyze sampling rate
Trim, resample, and save output files
Visualize spectrum
Notes
WAV files use stereo (L = I, R = Q).
If WAV header Fs and user-input Fs differ, the header value takes priority.
Frequency axis is correctly drawn as complex baseband (−Fs/2 to +Fs/2).
