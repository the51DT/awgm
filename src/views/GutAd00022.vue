<template>
  <v-app>
    <v-main class="pa-10">
      <v-card class="custom" flat>
        <v-card-title class="card-title">회원 상세</v-card-title>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>아이디</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>36733232081</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>이름</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>고주영</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>연락처</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>01045802686</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>출생년도</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>1977</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>성별</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>남성</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>가입일자</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>20241201</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>인증횟수</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>1</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>ABO 인증</span>
          </v-col>
          <v-col cols="10" class="d-flex align-center">
            <span>인증 완료</span>
            <v-btn class="ml-2 large" variant="outlined">인증해제</v-btn>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>다타익선 인증</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>인증 완료</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>바디키 인증</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>미인증</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>그로잉 랩</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>인증 완료</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>자녀계정</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>5개 생성(ab1, ab2, ab3, ab4, ab5)</span>
          </v-col>
        </v-row>

        <v-row class="input-row" align="center">
          <v-col cols="2">
            <span>최근접속일시</span>
          </v-col>
          <v-col cols="10" class="d-flex">
            <span>2024-12-01 08:00</span>
          </v-col>
        </v-row>

        <v-row class="footer-row">
          <v-col cols="2" class="d-flex justify-start">
            <v-btn class="large" variant="flat">강제탈퇴</v-btn>
          </v-col>

          <v-col cols="10" class="d-flex justify-end">
            <v-btn class="large" variant="outlined">목록</v-btn>
          </v-col>
        </v-row>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "GutAd00022",
};
</script>
