<template>
  <v-app>
    <v-main class="pa-10">
      <v-card class="custom" flat>
        <v-card-title class="card-title">챌린지 수정</v-card-title>
        <div class="scroll-area">
          <v-row class="input-row" align="center">
            <v-col cols="2">
              <span>메인 챌린지명 *</span>
            </v-col>
            <v-col cols="10" class="d-flex">
              <v-text-field
                :loading="loading"
                density="compact"
                label="챌린지명을 입력해 주세요."
                variant="outlined"
                hide-details
                single-line
                @click:append-inner="onClick"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row class="input-row">
            <v-col cols="2">
              <span>챌린지 안내문구</span>
            </v-col>
            <v-col cols="10" class="d-flex">
              <v-textarea
                :loading="loading"
                density="compact"
                label="챌린지 안내문구를 입력해주세요"
                variant="outlined"
                hide-details
                single-line
                @click:append-inner="onClick"
              ></v-textarea>
            </v-col>
          </v-row>
          <v-row class="input-row" align="center">
            <v-col cols="2">
              <span>참여 팀원수 *</span>
            </v-col>
            <v-col cols="10" class="d-flex">
              <span class="mr-4 d-flex align-center">최소인원</span>
              <v-text-field
                :loading="loading"
                density="compact"
                label=""
                variant="outlined"
                hide-details
                single-line
                @click:append-inner="onClick"
              ></v-text-field>
              <span class="ml-4 mr-4 d-flex align-center">~</span>
              <span class="mr-4 d-flex align-center">최대인원</span>
              <v-text-field
                :loading="loading"
                density="compact"
                label=""
                variant="outlined"
                hide-details
                single-line
                @click:append-inner="onClick"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row class="input-row mt-6" align="center">
            <v-col cols="10">
              <h3>서브 챌린지 설정</h3>
            </v-col>
            <v-col cols="2" class="d-flex justify-end">
              <v-btn class="large" variant="flat">+추가</v-btn>
            </v-col>
          </v-row>
          <v-sheet class="mt-4 pa-8" border="sm" rounded="lg">
            <v-row class="input-row" align="center">
              <v-col cols="12">
                <h4>서브 챌린지 01</h4>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>챌린지 명 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-text-field
                  :loading="loading"
                  density="compact"
                  label="챌린지명을 입력해 주세요."
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>챌린지 기간 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-date-input
                  :loading="loading"
                  density="compact"
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                  prepend-icon=""
                  append-inner-icon="$calendar"
                ></v-date-input>
                <span class="ml-4 mr-4 d-flex align-center">~</span>
                <v-date-input
                  :loading="loading"
                  density="compact"
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                  prepend-icon=""
                  append-inner-icon="$calendar"
                ></v-date-input>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>챌린지 노출기간 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-date-input
                  :loading="loading"
                  density="compact"
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                  prepend-icon=""
                  append-inner-icon="$calendar"
                ></v-date-input>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>성공 조건 타입 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-radio-group v-model="successCondition" inline hide-details>
                  <v-radio value="certification">
                    <template v-slot:label>
                      <div>인증률</div>
                      <v-text-field
                        :loading="loading"
                        density="compact"
                        label=""
                        variant="outlined"
                        hide-details
                        single-line
                        @click:append-inner="onClick"
                        class="ml-4 mr-2"
                      ></v-text-field>
                      <div>% 이상</div>
                    </template>
                  </v-radio>
                  <v-radio value="number" class="ml-4">
                    <template v-slot:label>
                      <div>개인 인증횟수</div>
                      <v-text-field
                        :loading="loading"
                        density="compact"
                        label=""
                        variant="outlined"
                        hide-details
                        single-line
                        @click:append-inner="onClick"
                        class="ml-4 mr-2"
                      ></v-text-field>
                      <div>회 이상</div>
                    </template>
                  </v-radio>
                </v-radio-group>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>보상 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-radio-group v-model="amends" inline hide-details>
                  <v-radio label="바우처" value="voucher"></v-radio>
                  <v-radio
                    label="ABC 수령"
                    value="receive"
                    class="ml-4"
                  ></v-radio>
                  <v-radio
                    label="바우처 + ABC 수령"
                    value="both"
                    class="ml-4"
                  ></v-radio>
                  <v-radio label="보상 없음" value="nix" class="ml-4"></v-radio>
                </v-radio-group>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>보상명</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-text-field
                  :loading="loading"
                  density="compact"
                  label="보상명을 입력해 주세요."
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row class="input-row">
              <v-col cols="12" class="d-flex justify-end">
                <v-btn class="ml-2 large" variant="flat" color="red"
                  >-삭제</v-btn
                >
              </v-col>
            </v-row>
          </v-sheet>
          <v-sheet class="mt-4 pa-8" border="sm" rounded="lg">
            <v-row class="input-row" align="center">
              <v-col cols="12">
                <h4>서브 챌린지 02</h4>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>챌린지 명 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-text-field
                  :loading="loading"
                  density="compact"
                  label="챌린지명을 입력해 주세요."
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>챌린지 기간 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-date-input
                  :loading="loading"
                  density="compact"
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                  prepend-icon=""
                  append-inner-icon="$calendar"
                ></v-date-input>
                <span class="ml-4 mr-4 d-flex align-center">~</span>
                <v-date-input
                  :loading="loading"
                  density="compact"
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                  prepend-icon=""
                  append-inner-icon="$calendar"
                ></v-date-input>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>챌린지 노출기간 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-date-input
                  :loading="loading"
                  density="compact"
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                  prepend-icon=""
                  append-inner-icon="$calendar"
                ></v-date-input>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>성공 조건 타입 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-radio-group v-model="successCondition" inline hide-details>
                  <v-radio value="certification">
                    <template v-slot:label>
                      <div>인증률</div>
                      <v-text-field
                        :loading="loading"
                        density="compact"
                        label=""
                        variant="outlined"
                        hide-details
                        single-line
                        @click:append-inner="onClick"
                        class="ml-4 mr-2"
                      ></v-text-field>
                      <div>% 이상</div>
                    </template>
                  </v-radio>
                  <v-radio value="number" class="ml-4">
                    <template v-slot:label>
                      <div>개인 인증횟수</div>
                      <v-text-field
                        :loading="loading"
                        density="compact"
                        label=""
                        variant="outlined"
                        hide-details
                        single-line
                        @click:append-inner="onClick"
                        class="ml-4 mr-2"
                      ></v-text-field>
                      <div>회 이상</div>
                    </template>
                  </v-radio>
                </v-radio-group>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>보상 *</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-radio-group v-model="amends" inline hide-details>
                  <v-radio label="바우처" value="voucher"></v-radio>
                  <v-radio
                    label="ABC 수령"
                    value="receive"
                    class="ml-4"
                  ></v-radio>
                  <v-radio
                    label="바우처 + ABC 수령"
                    value="both"
                    class="ml-4"
                  ></v-radio>
                  <v-radio label="보상 없음" value="nix" class="ml-4"></v-radio>
                </v-radio-group>
              </v-col>
            </v-row>
            <v-row class="input-row" align="center">
              <v-col cols="2">
                <span>보상명</span>
              </v-col>
              <v-col cols="10" class="d-flex">
                <v-text-field
                  :loading="loading"
                  density="compact"
                  label="보상명을 입력해 주세요."
                  variant="outlined"
                  hide-details
                  single-line
                  @click:append-inner="onClick"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row class="input-row">
              <v-col cols="12" class="d-flex justify-end">
                <v-btn class="ml-2 large" variant="flat" color="red"
                  >-삭제</v-btn
                >
              </v-col>
            </v-row>
          </v-sheet>
        </div>
        <v-row class="footer-row">
          <v-col cols="2" class="d-flex justify-start">
            <v-btn class="large" variant="flat">삭제</v-btn>
          </v-col>
          <v-col cols="10" class="d-flex justify-end">
            <v-btn class="large" variant="outlined">목록</v-btn>
            <v-btn class="ml-2 large" variant="flat">저장</v-btn>
          </v-col>
        </v-row>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "GutAd00028",
  data() {
    return {
      successCondition: "certification",
      amends: "voucher",
    };
  },
};
</script>
