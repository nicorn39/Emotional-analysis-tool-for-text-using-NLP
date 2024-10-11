import streamlit as st
import nltk
from nltk.sentiment import SentimentIntensityAnalyzer

# 必要なデータをダウンロード
nltk.download('vader_lexicon')

# 背景色を変更するためのCSSを追加
st.markdown(
    """
    <style>
    .stApp {
        background-color: lightblue;
    }
    </style>
    """,
    unsafe_allow_html=True
)

# タイトル
st.title("Emotional analysis tool for text using NLP(感情分析ツール)")

# ユーザーからテキスト入力を受け取る
text = st.text_area("Please enter the text you wish to analyze（分析したいテキストを入力してください）:")

if text:
    # 感情分析
    sia = SentimentIntensityAnalyzer()
    sentiment = sia.polarity_scores(text)

    # 結果の表示
    st.subheader("Emotional Analysis Results(感情分析結果)")
    st.write(f"positive(ポジティブ度): {sentiment['pos']}")
    st.write(f"negative(ネガティブ度): {sentiment['neg']}")
    st.write(f"neutrality(中立度): {sentiment['neu']}")
    st.write(f"Total Score(合計スコア): {sentiment['compound']}")  # 総合的な感情スコア

    # テキストの要約
    st.subheader("summarization(要約)")
    sentences = text.split('. ')  # 文の分割（文末のピリオドで）
    summary = " ".join(sentences[:3])  # 最初の3文を要約
    st.write(summary)
