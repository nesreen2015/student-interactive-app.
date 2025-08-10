import streamlit as st

st.set_page_config(page_title="برنامج تفاعلي للطلاب", page_icon=":books:", layout="centered")

st.title("برنامج تفاعلي للطلاب")

# إدخال الاسم
name = st.text_input("اكتب اسمك:")

if st.button("اضغط للترحيب"):
    if name.strip() == "":
        st.warning("يرجى إدخال الاسم أولًا.")
    else:
        st.success(f"مرحباً يا {name}!")

st.markdown("---")

# سؤال اختيار من متعدد
st.subheader("اختر الإجابة الصحيحة:")
question = "ما عاصمة مصر؟"
options = ["القاهرة", "الرياض", "دمشق", "الجزائر"]
answer = st.radio(question, options, key="answer")

if st.button("تحقق من الإجابة"):
    if answer == "القاهرة":
        st.balloons()
        st.success("إجابة صحيحة! أحسنت 👏")
    else:
        st.error("إجابة غير صحيحة. حاول مرة أخرى!")
