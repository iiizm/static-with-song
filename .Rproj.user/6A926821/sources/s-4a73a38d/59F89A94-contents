for(i in c("shinydashboard","shiny","leaflet","ggplot2","devtools","shinythemes","fmsb","plotly","dplyr","DBI","httr","DT","shinycssloaders",
           "canvasXpress","radarchart")){
  library(i, character.only = T)
} 
library(MVN)
library(shinyBS)
library(shinyjs)
test1 = "일반통계 분석모듈"
test2 = "기초통계, 연관관계, 차이, 인과관계 분석을 위한 곳입니다."
test3 = "현재는 데이터 업로드, 빈도분석, 기술통계분석 구조방정식모델(SEM)분석만 가능하지만 점차 업데이트 예정입니다."
test4 = "이곳은 체계도이고 실제 분석은 왼쪽메뉴를 선택해서 진행하세요."
#dd = HTML(paste0(test1,tags$br(),test2,tags$br(),test3)


source("chooser.R")
options(shiny.sanitize.errors = TRUE)
#===== use insertUI(), removeUI()
shinyUI(dashboardPage(skin="blue",
                      dashboardHeader(title = "일반통계 분석모듈",
                                      titleWidth = 1500),
                      dashboardSidebar(useShinyjs(),
                                       collapsed = F,
                                       width = 250,
                                       sidebarMenu(id = "sidebar",
                                                   br(),
                                                   #hidden(tags$div(class="header", id="haha", menuItem("", tabName = "home", icon = icon("home")))),
                                                   menuItem("",
                                                            tabName = 'home',
                                                            icon = icon('home')
                                                   ),
                                                   menuItem('데이터 업로드 및 저장', 
                                                            tabName = 'dtupload',
                                                            icon = icon('cloud-upload')
                                                   ),
                                                   menuItem('빈도분석', 
                                                            tabName = 'frequency',
                                                            icon = icon('signal')
                                                   ),
                                                   menuItem('기술통계분석', 
                                                            tabName = 'description',
                                                            icon = icon('calculator')
                                                   ),
                                                   menuItem('연관관계분석', 
                                                            icon = icon('link'),
                                                            hr(),
                                                            menuItem('교차분석',
                                                                     tabName = 'cross',
                                                                     icon = icon('refresh')),
                                                            hr(),
                                                            menuItem('상관분석',
                                                                     tabName = 'correlation',
                                                                     icon = icon('refresh')),
                                                            hr()
                                                            
                                                   ),
                                                   menuItem('차이분석', 
                                                            icon = icon('arrows-h'),
                                                            hr(),
                                                            menuItem('독립표본 t-test분석',
                                                                     tabName = 'ttest',
                                                                     icon = icon('refresh')),
                                                            hr(),
                                                            menuItem(HTML(paste0("일원배치분산",
                                                                                 tags$br(),
                                                                                 "&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(ANOVA)분석")),
                                                                     tabName = 'anova',
                                                                     icon = icon('refresh')),
                                                            hr()
                                                   ),
                                                   menuItem('인과관계분석', 
                                                            icon = icon('sign-in'),
                                                            hr(),
                                                            menuItem('회귀분석',
                                                                     tabName = 'regression',
                                                                     icon = icon('refresh')),
                                                            hr(),
                                                            menuItem(HTML(paste0("구조방정식",
                                                                                 tags$br(),
                                                                                 "&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;모델(SEM)분석")),
                                                                     
                                                                     icon = icon('refresh'),
                                                                     menuItem('구조방정식 분석 절차', 
                                                                              tabName = 'structural'
                                                                     ),
                                                                     menuItem('다변량 정규성 검증', 
                                                                              tabName = 'choo'
                                                                     ),
                                                                     menuItem('구조방정식 모델', 
                                                                              tabName = 'editequation'
                                                                     )
                                                                     
                                                            ),
                                                            hr()
                                                   )
                                                   
                                                   
                                       )
                      ),
                      dashboardBody(tags$head(tags$script(src = "message-handler.js")),
                                    tags$style(HTML(".sidebar-menu li a { padding : 18px 5px;}
                                                    .box-solid { display:table;}
                                                    .box-body { display:table-cell; vertical-align: middle; text-align: center;}
                                                    .skin-red .main-header .logo { font-weight:bold;}
                                                    #list { text-align: left;}
                                                    .col-sm-7 { padding-right: 0;}
                                                    .model-title { font-size: 20pt; font-weight: 800;}
                                                    .model-left { padding-right: 7px; }
                                                    .model-right { padding-left: 7px; }
                                                    .model-box { height: 400px; }
                                                    .sem-process { text-align: left; word-break:break-all; }")),
                                    
                                    tabItems(
                                      tabItem(tabName = "home",
                                              
                                              fluidRow(
                                                column(12,
                                                       box(width = "100%", height = "75px", background = "navy", align="center",
                                                           h2("일반통계 분석모듈"),
                                                           h4("기초통계, 연관관계, 차이, 인과관계 분석을 위한 곳입니다."),
                                                           h4("현재는 데이터 업로드, 빈도분석, 기술통계분석 구조방정식모델(SEM)분석만 가능하지만 점차 업데이트 예정입니다."),
                                                           h4("이곳은 체계도이고 실제분석은 왼쪽메뉴를 선택해서 진행하세요.")
                                                       )
                                                ),
                                                column(2,
                                                       box(width = "100%", height = "35px", background = "navy", align="center", class="home-text",
                                                           "데이터 업로드 및 저장"),
                                                       box(width = "100%", height = "78px", background = "navy", align="center",class="home-text",
                                                           "빈도 분석"),
                                                       box(width = "100%", height = "35px", background = "navy", align="center", class="home-text",
                                                           "기술 통계 분석"),
                                                       column(5, style='padding:0px;',
                                                              box(width = "100%", height = "100px", background = "navy", align="center", class="home-text",
                                                                  "연관 관계 분석"),
                                                              box(width = "100%", height = "178px", background = "navy", align="center", class="home-text",
                                                                  "차이 분석"),
                                                              box(width = "100%", height = "137px", background = "navy", align="center", class="home-text",
                                                                  "인과 관계 분석")),
                                                       column(7,
                                                              box(width = "100%", height = "35px", background = "navy", align="center", class="home-text",
                                                                  "교차 분석"),
                                                              box(width = "100%", height = "35px", background = "navy", align="center", class="home-text",
                                                                  "상관 분석"),
                                                              box(width = "100%", height = "78px", background = "navy", align="center", class="home-text",
                                                                  "독립표본 t-test 분석"),
                                                              box(width = "100%", height = "80px", background = "navy", align="center", class="home-text",
                                                                  "일원배치분산 분석(ANOVA)"),
                                                              box(width = "100%", height = "35px", background = "navy", align="center", class="home-text",
                                                                  "회귀 분석"),
                                                              box(width = "100%", height = "78px", background = "navy", align="center", class="home-text",
                                                                  "구조방정식모델"))
                                                ),
                                                br(),
                                                br(),
                                                column(6,
                                                       box(width = "100%", height = "35px", background = "blue", class="home-text",
                                                           "통계분석을 실시할 수 있도록 데이터를 분석모듈에 업로드 및 저장"),
                                                       box(width = "100%", height = "78px", background = "blue", class="home-text",
                                                           h5("질적변수(명목, 서열변수)에 대해 빈도분석 실시"),
                                                           h6("빈도 : 하나의 질적변수내에서 각각의 보기가 자주 나타난 정도를 의미")),
                                                       box(width = "100%", height = "35px", background = "blue", class="home-text",
                                                           "양적변수(등간, 연속변수)에 대해 기술통계치(합계, 평균 등) 도출"),
                                                       box(width = "100%", height = "35px", background = "blue", class="home-text",
                                                           "질적변수(명목, 서열변수)간 연관관계 분석"),
                                                       box(width = "100%", height = "35px", background = "blue", class="home-text",
                                                           "양적변수(등간, 연속변수)간 연관관계 분석"),
                                                       box(width = "100%", height = "78px", background = "blue", class="home-text",
                                                           h5("질적변수에 따른 양적변수 차이 분석"),
                                                           h6("질적변수의 선택보기 2개인 경우, 예) 남자&여자")),
                                                       box(width = "100%", height = "80px", background = "blue", class="home-text",
                                                           h5("질적변수에 따른 양적변수 차이 분석"),
                                                           h6("질적변수의 선택보기 3개 이상인 경우, 예) 서울&수도권&지방")),
                                                       box(width = "100%", height = "35px", background = "blue", class="home-text",
                                                           "양적변수 간 단순한 인과관계 분석"),
                                                       box(width = "100%", height = "78px", background = "blue", class="home-text",
                                                           h5("양적변수 간 복잡한 인과관계 분석"),
                                                           h6("복잡한 인과관계 : 회귀분석과 비교해 볼 때 종속변수가 여러 개이거나 여러 단계의 인과관계를 동시에 분석해야 하는 경우"))
                                                ),
                                                column(4,
                                                       box(width = "100%", height = "674px", background = "light-blue", class="home-text",
                                                           h3("분석기법 선택 시 참고사항"),
                                                           br(),
                                                           h5("- 변수: 분석대상이 되는 관심대상. 설문지의 경우 하나하나의 질문항목들을 의미함."),
                                                           br(),
                                                           h5("- 명목변수: 구분만 가능한 변수"),
                                                           h5("예) 당신의 성별은? 남자/여자"),
                                                           br(),
                                                           h5("- 서열변수: 순위구분이 가능한 변수"),
                                                           h5("예) 당신의 교육수준은? 초졸/중졸/고졸이상"),
                                                           br(),
                                                           h5("- 등간변수: 보기간 간격이 동일하여 변수간 더하기 빼기 가능"),
                                                           h5("예) 레스토랑 이용만족도는 어떠한가요? 전혀 그렇지 않다/보통이다/매우 그렇다"),
                                                           br(),
                                                           h5("- 연속변수: 완전히 숫자로 취급이 가능하여 사칙연산이 가능"),
                                                           h5("예) 당신의 소득은? _____ 만원"),
                                                           br(),
                                                           h5("- 질적변수: 명목과 서열변수를 의미"),
                                                           h5("- 양적변수: 등간과 연속변수를 의미"))),
                                                column(12,
                                                       actionButton("close", "초기화면으로 이동", onclick ="location.href='http://ksdsi.co.kr';", width="100%",
                                                                    style = "background-color: #D81B60; color: white;"))
                                              )
                                              
                                      ),
                                      tabItem(tabName = "dtupload",
                                              fluidRow(
                                                column(12,
                                                       column(3,
                                                              # Input: Select a file ----
                                                              fileInput("file", label = "파일 업로드(csv, xlsx)")),
                                                       column(8, 
                                                              box(width = "100%", height = "50px", background = "navy", 
                                                                  h5("분석하고자 하는 자료를 업로드 하세요. 현재 지원가능 파일 형식은 csv, xlsx입니다."),
                                                                  h5("다른 형식의 파일은 csv나 xlsx형식으로 바꾸어 업로드해주세요."),
                                                                  br(),
                                                                  h5("또한 추후 분석 시 결측치(빈칸)가 존재하면 분석 중 에러가 발생할 수 있으니 참고하시기 바랍니다.")))
                                                )
                                              ),
                                              
                                              
                                              # Horizontal line ----
                                              tags$hr(),
                                              
                                              # Input: Checkbox if file has header ----
                                              #checkboxInput("header", "Header", TRUE),
                                              h4("데이터 테이블"),
                                              DT::dataTableOutput("table", width = 1000),
                                              br(),
                                              fluidRow(
                                                column(2,
                                                       actionButton("saveData", "확인된 데이터 저장")
                                                ),
                                                column(2, offset = 1,
                                                       actionButton("downloadData", "데이터 다운로드")
                                                ),
                                                column(2, offset = 1,
                                                       actionButton("goMenu", "분석 모듈로 이동")
                                                )
                                              )
                                              
                                      ),
                                      tabItem(tabName = "selectvar",
                                              verbatimTextOutput("listbox"),
                                              uiOutput("selectColumn"),
                                              verbatimTextOutput("listbox2"),
                                              uiOutput("selectedColumn")
                                      ),
                                      tabItem(tabName = "structural",
                                              h2("구조방정식 분석 절차"),
                                              br(),
                                              fluidRow(
                                                column(8, align="center",
                                                       img(src = "img.png",align = "center", width = 800, height = 700)
                                                ),
                                                column(4,
                                                       box(width = "100%", height = "100%", background = "light-blue", class="sem-process",
                                                           p(class="sem-process-1",
                                                             HTML(paste0("본 분석기법은 기존 구조방정식 모델 패키지인 AMOS, LISREL, EQS, Mplus가 아니라 R프로그램내 Lavaan패키지에 기반하고 있습니다. 기존 패키지들과는 분석순서와 결과는 거의 같아서 향후 발전가능성이 높은 편이나 모델설정 방법 등에서는 차이가 있으니 이에 대해 충분히 살펴보고 진행하는 것을 권해드립니다. 일반적인 구조방정식 이외의 기법들은 향후 업데이트 예정입니다. 많은 관심 바랍니다. 궁금한 점은 송학준(bloodia00@hanmail.net)으로 연락주세요. 관련 참고문헌은 다음과 같습니다."))
                                                           ),
                                                           p(class= "sem-process-2",
                                                             HTML(paste0("Robust추정치에 대한 카이제곱 차이검정",tags$br(),
                                                                         "- Chi-Square difference test for MLR in Mplus.xlsx",tags$br(),
                                                                         "https://fhssrsc.byu.edu/Documents/Chi-Square%20difference%20test%20for%20MLR%20in%20Mplus.xlsx",tags$br(),
                                                                         tags$br(),
                                                                         "ML추정치에 대한 카이제곱 차이검정",tags$br(),
                                                                         "- SEM Stats - Watoo Watoo",tags$br(),
                                                                         "http://www.watoowatoo.net/sem/sem_stats.xls",tags$br(),
                                                                         tags$br(),
                                                                         "영문 참고문헌:",tags$br(),
                                                                         "- The lavaan Project, http://lavaan.ugent.be/",tags$br(),
                                                                         "- The lavaan tutorial, http://lavaan.ugent.be/tutorial/tutorial.pdf",tags$br(),
                                                                         "- Confirmatory Factor Analysis in lavaan with examples, http://www.amarkos.gr/research/lavaan/",tags$br(),
                                                                         tags$br(),
                                                                         "국문 참고문헌:",tags$br(),
                                                                         "- R을 활용한 SEM – lavaan – philosopher's cooking club,",tags$br(),
                                                                         "https://sojungluciakim.wordpress.com/2016/03/11/r%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-sem-lavaan/",tags$br(),
                                                                         "- 웹에서 하는 R통계,",tags$br(),
                                                                         "http://web-r.org/index.php?mid=webrboard&page=2",tags$br(),
                                                                         "- DataBaser.Net: 구조방정식,",tags$br(),
                                                                         "http://www.databaser.net/moniwiki/wiki.php/%EA%B5%AC%EC%A1%B0%EB%B0%A9%EC%A0%95%EC%8B%9D",tags$br(),
                                                                         "- 백영민(2017) R를 이용한 사회과학 데이터 분석(구조방정식모형 분석), 커뮤니케이션북스.",tags$br(),
                                                                         "- 김계수(2015) R-구조방정식 모델링, 한나래 아카데미."
                                                             )))
                                                       )
                                                )
                                              )
                                              
                                      ),
                                      # tabItem(tabName = "result",
                                      #         h4("Summary"),
                                      #         verbatimTextOutput("summary"),
                                      #         br(),
                                      #         h4("semplot"),
                                      #         plotOutput("Plot")
                                      # ),
                                      tabItem(tabName = "choo",
                                              fluidRow(
                                                column(6, align="center",
                                                       br(),
                                                       br(),
                                                       uiOutput("Chooser"),
                                                       br(),
                                                       br(),
                                                       actionButton("collist", "다변량 정규성 검증"),
                                                       bsModal("d_result", "SEM Result", "collist",
                                                               size="large", verbatimTextOutput("list"), actionButton("multi_download", "Download to PDF"))
                                                ),
                                                column(3, align="center",
                                                       br(),
                                                       br(),
                                                       box(width = "100%", height = "350px", background = "light-blue", align="center", style="padding:5px",
                                                           h4("1. 다변량 정규성 검정 분석 방법"),
                                                           br(),
                                                           h5("구조방정식 모델에서 사용되는 모든 변수를 선택하여 분석을 진행하면 됩니다."),
                                                           br(),
                                                           h4("2. 다변량 정규성 검정 결과 해석 방법"),
                                                           br(),
                                                           br(),
                                                           h5("해당 구조방정식 모델 분석모듈은 다변량 정규분포가정 검증에 Mardia의 표준화계수를 이용하고 있습니다. 본 분석에서 Mardia의 표준화계수는 z.kurtosis값을 의미합니다."),
                                                           br(),
                                                           h5("Mardia의 표준화계수가 기준치(5)를 상회하는 경우 수집된 자료는 다변량 정규분포 가정을 만족하지 못하는 것으로 간주됩니다."),
                                                           br(),
                                                           h5("이 경우 최대우도법(ML)의 대체 추정방법으로 안정 최대우도법(Robust ML)을 사용하면 보다 안정되고 유효한 모형적합도 및 계수추정치를 얻을 수 있습니다."),
                                                           br(),
                                                           h5("분석 시 결측치(빈칸)가 존재하면 분석 중 에러가 발생할 수 있습니다.")
                                                       )
                                                )
                                              )
                                              
                                              #verbatimTextOutput("list2")
                                              #tableOutput("table2")
                                      ),
                                      tabItem(tabName = "frequency", 
                                              box(title = "빈도 분석", width = "100%",
                                                  h5("질적변수 (명목, 서열변수) 에 대해 빈도분석 실시하는 곳입니다.")
                                              ),
                                              selectInput("select_var1", "변수 선택", "", multiple=FALSE, selectize=TRUE),
                                              actionButton("freq_run", "분석 실시"),
                                              actionButton("return", "일반통계 분석모듈로 이동 하기"),
                                              bsModal("freq", "Frequency Result", "freq_run", size="large", plotOutput("freq_plot"), verbatimTextOutput("freq_result"))
                                      ),
                                      tabItem(tabName = "description", 
                                              box(title = "기술 통계 분석", width = "100%",
                                                  h5("양적변수 (등간, 연속변수) 에 대해 기술통계치 (합계, 평균 등) 도출하는 곳입니다.")
                                              ),
                                              selectInput("select_var2", "변수 선택", "", multiple=TRUE, selectize=TRUE),
                                              actionButton("static_run", "분석 실시"),
                                              actionButton("return2", "일반통계 분석모듈로 이동 하기"),
                                              bsModal("static", "Descriptive Statistics Result", "static_run", size="large", verbatimTextOutput("static_result"))
                                      ),
                                      tabItem(tabName = "cross", 
                                              box(title = "교차 분석", width = "100%",
                                                  h5("질적변수(명목, 서열변수)간 연관관계를 분석하고 분석결과에 대한 통계적 유의성을 알아보는 곳입니다."),
                                                  h5("향후 업데이트 예정입니다. 현재는 데이터 업로드, 구조방정식모델(SEM)분석만 가능합니다.")
                                              ),
                                              actionButton("return3", "일반통계 분석모듈로 이동 하기")
                                      ),
                                      tabItem(tabName = "correlation", 
                                              box(title = "상관 분석", width = "100%",
                                                  h5("질적변수(명목, 서열변수)간 연관관계를 분석하고 분석결과에 대한 통계적 유의성을 알아보는 곳입니다."),
                                                  h5("향후 업데이트 예정입니다. 현재는 데이터 업로드, 구조방정식모델(SEM)분석만 가능합니다.")
                                              ),
                                              actionButton("return4", "일반통계 분석모듈로 이동 하기")
                                      ),
                                      tabItem(tabName = "ttest", 
                                              box(title = "독립표본 t-test 분석", width = "100%",
                                                  h5("질적변수에 따른 양적변수 차이 분석 (질적변수의 선택보기 2개인 경우,예) 남자&여자)"),
                                                  h5("향후 업데이트 예정입니다. 현재는 데이터 업로드, 구조방정식모델(SEM)분석만 가능합니다.")),
                                              actionButton("return5", "일반통계 분석모듈로 이동 하기")
                                      ),
                                      tabItem(tabName = "anova", 
                                              box(title = "일원배치분산(ANOVA) 분석", width = "100%",
                                                  h5("질적변수에 따른 양적변수 차이 분석(질적변수의 선택보기 3개이상인 경우,예) 서울&수도권&기타)"),
                                                  h5("향후 업데이트 예정입니다. 현재는 데이터 업로드, 구조방정식모델(SEM)분석만 가능합니다.")
                                              ),
                                              actionButton("return6", "일반통계 분석모듈로 이동 하기")
                                      ),
                                      tabItem(tabName = "regression", 
                                              box(title = "회귀 분석", width = "100%",
                                                  h5("양적변수간 단순한 인과관계를 분석하는 곳입니다. 독립변수는 여러 개일 수 있으나 종속변수는 1개만 분석이 가능합니다. 보다 복잡한 인과관계의 경우에는 구조방정식모델을 이용하세요."),
                                                  h5("향후 업데이트 예정입니다. 현재는 데이터 업로드, 구조방정식모델(SEM)분석만 가능합니다.")
                                              ),
                                              actionButton("return7", "일반통계 분석모듈로 이동 하기")
                                      ),
                                      # tabItem(tabName = "choo_result",
                                      #         verbatimTextOutput("list"),
                                      #         tableOutput("table2")
                                      # ),
                                      tabItem(tabName = "editequation",
                                              
                                              fluidRow(
                                                column(12,class="model-title-box",
                                                       box( width="100%", height="100%", background = "navy", 
                                                            p("모델 설정", class="model-title")
                                                       ),
                                                       fluidRow(
                                                         column(6, class="model-left",
                                                                box( width="100%", background = "blue", class="model-box",
                                                                     p("1. 구조방정식 모델 참고지식", class="model-title"),
                                                                     p(HTML(paste0("구조방정식 모델은 간단히 말해 측정모델을 통해 형성된 잠재변수간의 복잡한 인과관계인 구조모델을 분석하는 통계기법이라고 할 수 있습니다.",tags$br(),
                                                                                   tags$br(),
                                                                                   "측정모델: 관측변수와 잠재변수간의 관계를 분석합니다.",tags$br(),
                                                                                   "구조모델: 잠재변수 간 인과관계를 분석합니다.",tags$br(),
                                                                                   tags$br(),
                                                                                   "관측변수: 설문지에서 관측되는(존재하는) 변수",tags$br(),
                                                                                   "잠재변수: 관측변수(들)의 공통된 특징으로 새롭게 만들어낸 요인변수",tags$br(),
                                                                                   "외생변수: 구조모델에서 원인이 되는 잠재변수",tags$br(),
                                                                                   "내생변수: 구조모델에서 결과가 되는 잠재변수",tags$br(),
                                                                                   "(잔차) (공)분산변수: 관측변수의 경우 관측변수의 변량 중 잠재변수를 기술하는데 사용되고 남은 변량을 의미하고, 잠재변수의 경우에는 관측변수들의 선형결합에 의해 설명되고 남은 변량을 의미. 이들 간 추가적 관계설정이 최적 모델도출에 도움이 될 수 있습니다.",tags$br(),
                                                                                   tags$br(),
                                                                                   "다변량 정규성 검증결과에 따라 다변량 정규성 만족/불만족을 선택해 주세요. 불만족 선택 시 Robust 결과치가 제공되고 만족 선택 시 최대우도법(ML) 추정치가 제공됩니다."
                                                                     )), class="model-content")
                                                                )
                                                         ),
                                                         column(6, class="model-right",
                                                                box( width="100%", background = "blue", class="model-box",
                                                                     p("2. 구조방정식 모델설정 참고사항", class="model-title"),
                                                                     p(HTML(paste0("변수 관계설정 방법",tags$br(),
                                                                                   "모델의 특성에 따라 해당 인수(결과변수, 원인변수, 결과변수 이름 등)를 입력하세요.",tags$br(),
                                                                                   "- 결과변수: 모델 설정 시 하나의 식에서 왼쪽에 위치하는 변수를 의미.",tags$br(),
                                                                                   "측정모델에서 잠재변수를 의미하고 구조모델에서는 내생변수를 의미.",tags$br(),
                                                                                   tags$br(),
                                                                                   "- 원인변수: 모델 설정 시 하나의 식에서 오른쪽에 위치하는 변수를 의미.",tags$br(),
                                                                                   "측정모델에서 관측변수를 의미하고 구조모델에서는 외생변수를 의미.",tags$br(),
                                                                                   tags$br(),
                                                                                   "(잔차) (공)분산간 관계 설정: 두 변수 이름이 같으면 변수 관계설정에서 해당 변수의 분산(또는 잔차 분산)을 나타내고 다르면 두 변수 사이의 (잔차)공분산을 나타냅니다.",tags$br(),
                                                                                   tags$br(),
                                                                                   "분석을 여러 번 하는 경우 구조방정식 분석모형 창의 수식을 따로 복사해 사용하시면 편리합니다.",tags$br(),
                                                                                   "주의할 점: 변수선택 시 잘못 선택하는 경우 반드시 해당 변수를 클릭하고 삭제를 진행해 주세요. 그렇지 않으면 화면전체의 이동이 발생할 수 있습니다."
                                                                     )), class="model-content")
                                                                )
                                                         )
                                                       )
                                                )
                                              ),
                                              fluidRow(
                                                column(2,
                                                       radioButtons("oknotok",
                                                                    "다변량 정규성 만족/불만족",
                                                                    choiceNames = c("다변량 정규성 만족",
                                                                                    "다변량 정규성 불만족"),
                                                                    choiceValues = c("ok", "notok"),
                                                                    selected = "ok"),
                                                       textInput("lefttext","결과변수 이름 입력(공백없이)",value=""),
                                                       br(),
                                                       selectInput("leftvar","결과변수 선택","",multiple=TRUE,selectize=TRUE)
                                                ),
                                                column(3,
                                                       wellPanel(radioButtons("operator", 
                                                                              "변수 관계설정", 
                                                                              choiceNames = c("[=~] : 결과변수가 원인변수에 따라 측정됨  (잠재변수 - 관측변수 관계)",
                                                                                              "[~] :  결과변수가 원인변수에 의해 결정됨  (잠재변수 - 잠재변수 관계)",
                                                                                              "[~~] : (잔차) (공)분산간 관계 (결과 - 원인 구분 없음)",
                                                                                              "[~1] : 절편(측정원점) 설정",
                                                                                              "[:=] : 임의의 값 설정",
                                                                                              "[==] :  변수 간 제약설정(동일)",
                                                                                              "[<] :   변수 간 제약설정(보다 작다)",
                                                                                              "[>] :   변수 간 제약설정(보다 크다)"),
                                                                              choiceValues=c("=~","~","~~","~1",":=","==","<",">"),
                                                                              selected="=~")
                                                       )
                                                ),
                                                column(2,
                                                       selectInput("rightvar","원인변수 선택","",multiple=TRUE,selectize=TRUE)
                                                ),
                                                column(1, 
                                                       br(),
                                                       actionButton("add","모형설정", width="100px"),
                                                       br(),
                                                       br(),
                                                       actionButton("reset","초기화", width="100px")
                                                ),
                                                column(2,
                                                       textAreaInput("equation","구조방정식 분석모형 창",rows=8,width=300, height="300px")
                                                )
                                              ),
                                              fluidRow(
                                                column(4,
                                                       verbatimTextOutput("EquationText"))
                                              ),
                                              fluidRow(
                                                column(12, align="center",
                                                       actionButton("run","분석 실시", width="180px",
                                                                    style = "background-color: #0073B7; color: white;"))
                                              ),
                                              bsModal("sem_result", h3("구조방정식 모델 분석 결과"), "run", size="large",
                                                      h4("모형 분석결과(그림)"), plotOutput("Plot"), h6("비표준화 계수값을 근거로 도출됨"), hr(),
                                                      h4("모형적합도(pvalue>0.05, Q(chisq/df)<=3, cfi>0.9, nfi>0.9, nnfi>0.9, rmsea<0.05)"), h5("ML방법에 의한 적합도"), verbatimTextOutput("measure1"), h5("Robust방법에 의한 적합도"), verbatimTextOutput("measure2"),
                                                      h5("설명력(R-square)"), verbatimTextOutput("r_square"), hr(),
                                                      h4("계수도출"), h5("잠재변수 간 계수(표준화 계수값)"), verbatimTextOutput("para_stand1"), h5("잠재변수 간 계수(비표준화 계수값)"), verbatimTextOutput("parameter1"),
                                                      h5("잠재변수-측정변수 간 계수(표준화 계수값)"), verbatimTextOutput("para_stand2"), h5("잠재변수-측정변수 간 계수(비표준화 계수값)"), verbatimTextOutput("parameter2"), 
                                                      h5("공분산(표준화 계수값)"), verbatimTextOutput("cor_stand"), h5("공분산(비표준화 계수값)"), verbatimTextOutput("corvar") ,hr(),
                                                      h4("수정지수(최적모형 도출에 도움이 될 수 있음)"), h5("수정지수 분석모형에 추가방법: [lhs op rhs]에서 해당 수식을 구조방정식 분석모형 창에 복사하여 붙여넣기 하면 됨"), h5("수정지수: 측정변수 간"), verbatimTextOutput("modi1"), 
                                                      h5("수정지수: 잠재변수-측정변수 간"), verbatimTextOutput("modi2"), h5("수정지수: 잠재변수 간"), verbatimTextOutput("modi3"), 
                                                      h4("집중타당성 참고자료"), h5("크론바하 알파(Cronbach's Alpha) : 0.7이상"), verbatimTextOutput("alpha"), h5("합성신뢰도(Composite Reliabiity) : 0.7이상"), verbatimTextOutput("CR"), h5("평균분산추출값(Average Variance Extracted) : 0.5이상"), verbatimTextOutput("ave"), 
                                                      hr(),
                                                      h4("판별타당성 참고자료"), h5("잠재변수 간 상관관계"), verbatimTextOutput("latent_cor"), h5("잠재변수 간 상관관계 제곱"), verbatimTextOutput("latent_cor_sqr"), 
                                                      h5("잠재변수 간 표준오차"), verbatimTextOutput("latent_std"),
                                                      actionButton("sem_download", "Download to PDF"))
                                              # 
                                              # verbatimTextOutput("EquationText"),
                                              # selectInput("leftvar","leftvar","",multiple=TRUE,selectize=TRUE),
                                              # textInput("lefttext","lefttext",value=""),
                                              # wellPanel(radioButtons("operator",
                                              #                        "operator",
                                              #                        choices=c("=~","~","~~",":=","==","<",">"),
                                              #                        selected="=~"),
                                              #           a(id = "toggleHelpOp", "?Operator")
                                              #           ),
                                              # selectInput("rightvar","rightvar","",multiple=TRUE,selectize=TRUE),
                                              # actionButton("add","add to equation"),
                                              # actionButton("reset","reset the equation"),
                                              # textAreaInput("equation","equation",rows=8,width=300),
                                              # actionButton("run","분석 실시"),
                                              # bsModal("sem_result", "SEM Result", "run",
                                              #         size="large", verbatimTextOutput("summary"),
                                              #         plotOutput("Plot"))
                                              
                                      )
                                      
                                      
                                    )
                                    # tabItem(tabName = "tab",
                                    #         tabsetPanel(id = "body",
                                    #           tabPanel("upload",
                                    #                    fileInput("file", label = "upload data"),
                                    #                    # Horizontal line ----
                                    #                    tags$hr(),
                                    #                    
                                    #                    # Input: Checkbox if file has header ----
                                    #                    checkboxInput("header", "Header", TRUE),
                                    #                    h4("DataTable"),
                                    #                    DT::dataTableOutput("table", width = 600),
                                    #                    br(),
                                    #                    actionButton("saveData", "확인된 데이터 저장"),
                                    #                    actionButton("downloadData", "데이터 다운로드"),
                                    #                    actionButton("goMenu", "분석 모듈로 이동")
                                    #                    ),
                                    #           tabPanel("view",
                                    #                    h4("Summary"),
                                    #                    verbatimTextOutput("summary"),
                                    #                    br(),
                                    #                    h4("semplot"),
                                    #                    plotOutput("Plot"))
                                    #         ),
                                    #         h2("negative")
                                    # )
                                    )
                      
                                    ))

# shinyUI(fluidPage(
#   #load js
#   tags$head(tags$script(src = "message-handler.js")),
#   # App title ----
#   titlePanel("SEM"),
#   br(),
#   
#   # Sidebar layout with input and output definitions ----
#   fluidRow(
#     
#     # Sidebar panel for inputs ----
#     column(3,
#            
#            "sidebar",
#            # Input: Select a file ----
#            fileInput("file", label = "upload data"),
#            # Horizontal line ----
#            tags$hr(),
#            
#            # Input: Checkbox if file has header ----
#            checkboxInput("header", "Header", TRUE)
#            
#            
#            
#            
#     ),
#     
#     # Main panel for displaying outputs ----
#     column(8,
#            
#            "mainpanel",
#            h4("DataTable"),
#            DT::dataTableOutput("table", width = 600),
#            br(),
#            
#            "buttonlayer",
#            fluidRow(
#              column(2, 
#                     actionButton("saveData", "확인된 데이터 저장")
#              ),
#              column(2, offset = 2,
#                     actionButton("downloadData", "데이터 다운로드")
#              ),
#              column(2, offset = 2,
#                     actionButton("goMenu", "분석 모듈로 이동")
#              )
#            ),
#            br(),
#            
#            fluidRow(
#              column(5,
#                     verbatimTextOutput("listbox"),
#                     uiOutput("selectColumn")
#              ),
#              column(5, offset = 2,
#                     verbatimTextOutput("listbox2"),
#                     uiOutput("selectedColumn")
#              )
#            ),
#            
#            
#            
#            # Output: Header + summary of distribution ----
#            h4("Summary"),
#            verbatimTextOutput("summary"),
#            br(),
#            
#            h4("semplot"),
#            plotOutput("Plot")
#            
#            
#     )
#     
#   )
# ))
