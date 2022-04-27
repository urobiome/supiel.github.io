<template>
<div class="content mainCon">

    <div class="container">
        <h2 class="logo"><span>Rex</span> 유로바이옴</h2>
        <b-card bg-variant="white" text-variant="dark" class="topCard">
            <b-card-text>
                안녕하세요,<br>
                수검자님<br><br>
                <span class="examDate">{{ examDate }}</span><br>
                검사결과 입니다.
            </b-card-text>
        </b-card>

        <b-card bg-variant="white" text-variant="dark" class="basicCard" header="마이크로바이옴 검사 결과">
            <b-card-text>
                <ul class="graphA">
                    <li>
                        <div class="graphAtitle">GU174097_g</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_GU174097_g_72.svg"></div>
                    </li>
                    <li>
                        <div class="graphAtitle">Bifidobacterium</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_Bifidobacterium_72.svg"></div>
                    </li>
                    <li>
                        <div class="graphAtitle">Collinsella</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_Collinsella_72.svg"></div>
                    </li>
                    <li>
                        <div class="graphAtitle">Blautia</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_Blautia_72.svg"></div>
                    </li>
                    <li>
                        <div class="graphAtitle">Ruminococcus_g2</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_Ruminococcus_g2_72.svg"></div>
                    </li>
                    <li>
                        <div class="graphAtitle">Escherichia</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_Escherichia_72.svg"></div>
                    </li>                   
                    <li>
                        <div class="graphAtitle">Klebsiella</div>
                        <div class="graphA1"><img src="../../public/img/Graph1_155_Klebsiella_72.svg"></div>
                    </li>
                    
                </ul>
            </b-card-text>
        </b-card>
        <ul class="graphPoint">
            <li>
                <b-icon icon="caret-down-fill" class="colorRed"></b-icon> 질환군 평균수치
            </li>
            <li>
                <b-icon icon="caret-down-fill" class="colorGreen"></b-icon> 정상군 평균수치
            </li>
            <li>
                <b-iconstack>
                    <b-icon stacked icon="record-fill" variant="white"></b-icon>
                    <b-icon stacked icon="record" class="colorBlue"></b-icon>                   
                </b-iconstack>
                 수검자님 수치
            </li>
        </ul>

        <b-card bg-variant="white" text-variant="dark" class="basicCard" header="질환 위험도 예측">
            <b-card-text>
                <ul class="graphB">
                    <li class="bottomMargin1">                      
                        <div class="graphB1"><img src="../../public/img/Graph2_155_T2D_72.svg"></div>
                        <div class="graphBtitle">
                            <div class="graphBtitleTop">당뇨 위험도 {{ diabetesPercent }}%</div>
                            <div class="graphBtitleNnder">10년 이내 발병 확률 
                                <span v-if="diabetesPercent >= 68" :class="rateColor[0]">{{ diabetesRate[0] }}</span>
                                <span v-else-if="diabetesPercent >= 34" :class="rateColor[1]">{{ diabetesRate[1] }}</span>
                                <span v-else-if="diabetesPercent >= 0" :class="rateColor[2]">{{ diabetesRate[2] }}</span>
                            </div>
                        </div>
                    </li>
                    <li>                      
                        <div class="graphB1"><img src="../../public/img/Graph2_155_Obesity_72.svg"></div>
                        <div class="graphBtitle">
                            <div class="graphBtitleTop">비만 위험도 {{ obesityPercent }}%</div>
                            <div class="graphBtitleNnder">10년 이내 발병 확률 
                                <span v-if="obesityPercent >= 68" :class="rateColor[0]">{{ obesityRate[0] }}</span>
                                <span v-else-if="obesityPercent >= 34" :class="rateColor[1]">{{ obesityRate[1] }}</span>
                                <span v-else-if="obesityPercent >= 0" :class="rateColor[2]">{{ obesityRate[2] }}</span>
                            </div>
                        </div>
                    </li>
                </ul>
            </b-card-text>
        </b-card>
        <ul class="graphPoint">
            <li>
                <b-icon icon="record-fill" class="colorRed"></b-icon> 높음
            </li>
            <li>
                <b-icon icon="record-fill" class="colorGreen"></b-icon> 주의
            </li>
            <li>
                <b-icon icon="record-fill" class="colorBlue"></b-icon> 낮음
            </li>
        </ul>

        <b-card>
            <b-card-text>
                수검자님의 마이크로바이옴 검사 결과는 다음과 같습니다. 10년 이내 당뇨 발병 위험도는 
                <span v-if="diabetesPercent >= 68" :class="rateColor[0]">{{ diabetesRate[0] }}</span>
                <span v-else-if="diabetesPercent >= 34" :class="rateColor[1]">{{ diabetesRate[1] }}</span>
                <span v-else-if="diabetesPercent >= 0" :class="rateColor[2]">{{ diabetesRate[2] }}</span> 단계이며, 
                비만의 발병 위험도가 
                <span v-if="obesityPercent >= 68" :class="rateColor[0]">{{ obesityRate[0] }}</span>
                <span v-else-if="obesityPercent >= 34" :class="rateColor[1]">{{ obesityRate[1] }}</span>
                <span v-else-if="obesityPercent >= 0" :class="rateColor[2]">{{ obesityRate[2] }}</span> 단계로 예상됩니다.
            </b-card-text>
        </b-card>

        <b-card bg-variant="white" text-variant="dark" class="basicCard" header="추천 관리 방법">
            <b-card-text>
                <ul>
                    <li>                      
                        <i class="fi fi-rr-restaurant"></i> 식이 관리
                        <ul class="cardList">
                            <span v-if="diabetesPercent >= 68">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateRedText[0] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateRedText[1] }}</li>
                            </span>
                            <span v-else-if="diabetesPercent >= 34">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateGreenText[0] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateGreenText[1] }}</li>
                            </span>
                            <span v-else-if="diabetesPercent >= 0">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateBlueText[0] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateBlueText[1] }}</li>
                            </span>
                        </ul>
                    </li>
                    <li>                      
                        <i class="fi fi-rr-gym"></i> 운동 관리
                        <ul class="cardList"> 
                            <span v-if="diabetesPercent >= 68">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateRedText[2] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateRedText[3] }}</li>
                            </span>
                            <span v-else-if="diabetesPercent >= 34">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateGreenText[2] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateGreenText[3] }}</li>
                            </span>
                            <span v-else-if="diabetesPercent >= 0">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateBlueText[2] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateBlueText[3] }}</li>
                            </span>
                        </ul>
                    </li>
                    <li>                      
                        <i class="fi fi-rr-bed"></i> 생활습관 관리
                        <ul class="cardList bottomNone">
                            <span v-if="diabetesPercent >= 68">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateRedText[4] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateRedText[5] }}</li>
                            </span>
                            <span v-else-if="diabetesPercent >= 34">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateGreenText[4] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateGreenText[5] }}</li>
                            </span>
                            <span v-else-if="diabetesPercent >= 0">
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateBlueText[4] }}</li>
                                <li><b-icon icon="check" class="colorBlue"></b-icon> {{ rateBlueText[5] }}</li>
                            </span>
                        </ul>
                    </li>
                </ul>
            </b-card-text>
        </b-card>
    </div>
</div>
</template>
<script>
export default {
    data() {
        return {
            examDate: '2022-01-27',
            diabetesRate: ['높음','주의','낮음'],
            diabetesPercent: 23,
            obesityRate: ['높음','주의','낮음'],
            obesityPercent: 33,
            rateColor: ['colorRed','colorGreen','colorBlue'],
            rateRedText: ['꿀, 성탕 등의 단순당이 많이 들어간 음식 줄이기','잡곡, 콩, 계란, 야채 골고루 섭취하기','전문가 조언에 따라 규칙적으로 운동하기','주 3회 20분간 숨이 찰 정도의 유산소 운동','금연/금주하기','주기적으로 병원 방문하여 검진하기'],
            rateGreenText: ['육류 대신 채식 위주의 식단으로 변경','3~4개의 반찬을 골고루 곁들어 먹기','5층 이하의 건물은 계단 이용하기','주 2회 20분간 숨이 찰 정도의 유산소 운동하기','과도한 스트레스 피하기','표준 체중 유지하기'],
            rateBlueText: ['규칙적으로 식사하기','달고 짠 음식 섭취 피하기','평소 활동량 늘리기','10분 미만의 거리는 걸어다니기','작은일에 화내지 않기','규칙적인 수면 시간 확보하기'],
        };
    },
};
</script>