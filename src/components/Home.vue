<template>
  <v-content>
    <v-container>
      <v-row>
        <v-col>
          <v-card>
            <v-img class="white--text align-end" height="200px" :src="curso.imgTopo"></v-img>
            <v-card-title>{{curso.titulo}}</v-card-title>
            <v-card-text>{{curso.subTitulo}}</v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Detalhes</v-card-title>
            <v-card-text>{{curso.detalhes}}</v-card-text>
          </v-card>
        </v-col>

        <v-col>
          <v-card>
            <v-card-title>Metodologia</v-card-title>
            <v-card-text>{{curso.metodologia}}</v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Tópicos</v-card-title>
            <v-card-text>
              <v-expansion-panels>
                <v-expansion-panel v-for="(item,i) in curso.topicos" :key="i">
                  <v-expansion-panel-header>{{item.titulo}}</v-expansion-panel-header>
                  <v-expansion-panel-content>{{item.sub}}</v-expansion-panel-content>
                </v-expansion-panel>
              </v-expansion-panels>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            <v-card-title>Estrutura</v-card-title>
            <v-container>
              <v-col>
                <v-card class="text-center pt-5 pb-5">
                  <img width="250" :src="curso.imagens[0].url" />
                </v-card>
              </v-col>
              <v-col>
                <v-card class="text-center pt-5 pb-5">
                  <img width="250" :src="curso.imagens[1].url" />
                </v-card>
              </v-col>
            </v-container>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Próxima Turma</v-card-title>
            <v-card-text>
              <ul>
                <li>{{curso.turma.inicio}}</li>

                <li>{{curso.turma.dias}}</li>

                <li>{{curso.turma.cargaHoraria}}</li>
              </ul>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col>
          <v-card>
            <v-card-title>Contato</v-card-title>
            <v-card-text>
              <v-container>
                <v-row>
                  <v-col>
                    <a
                      style="text-decoration: none;"
                      target="_blank"
                      href="http://bit.ly/whatsapp-ht2"
                    >
                      <v-icon>mdi-whatsapp</v-icon>
                      {{contato.whatsApp}}
                    </a>

                    <ul>
                      <li>{{contato.telefone}}</li>
                      <li>{{contato.email}}</li>
                    </ul>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Localização</v-card-title>
            <iframe
              width="100%"
              src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d119584.5497361193!2d-54.597575!3d-20.505522!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xa6ffe06c33e2057c!2sHigh%20Tech%20Cursos!5e0!3m2!1spt-BR!2sbr!4v1582244418152!5m2!1spt-BR!2sbr"
              height="450"
              frameborder="0"
              style="border:0;"
              allowfullscreen
            ></iframe>
          </v-card>
        </v-col>
      </v-row>

      <v-row class="text-center blue">
        <v-col>
          <img
            width="10%"
            src="https://www.fabricadeprogramador.com.br/img/logo-ht-white.fe4318dd.svg"
          />
        </v-col>
      </v-row>

      <v-row class="text-center blue">
        <v-col class="white--text">©Copyright 2020 High Tech Cursos - All Rights Reserved - Legal</v-col>
      </v-row>
    </v-container>
  </v-content>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      curso: {
        titulo: "Curso de Android - Kotlin",

        subTitulo: "devenvolvedor mobile",

        imgTopo: require("../assets/top2.png"),

        metodologia: `Todo o curso é baseado em metologia ativa 
                  utilizando o conceito de PBL (Problem Based Learning)
                  onde serão desevolvidos projetos basedo em problemas reais
                  proporcionando um aprendizado da tecnologia Android com Kotlin 
                  de forma totalmente aplicada.`,

        detalhes: `Este curso tem por objetivo 
                      introduzir os fundamentos do
                      desenvolvimento mobile para 
                      Android do básico, 
                      até o uso de frameworks, 
                      com manipulação de banco de dados local, 
                      requisições HTTP e uso de recursos de hardware.
            `,
        imagens: [
          {
            url: require("../assets/img1.jpg")
          },
          {
            url: require("../assets/img2.jpg")
          }
        ],
        turma: {
          inicio: "Início 05/06/2020",
          dias: "Todas as Sextas das 19:00 às 22:00",
          cargaHoraria: "Carga Horária: 40 horas",
          diasSemana: "Todas as Sextas das 19:00 às 22:00"
        },

        topicos: [
          { titulo: "Introdução ao Android", sub: "" },
          { titulo: "Arquitetura ao Android", sub: "" },
          {
            titulo: "Ambiente de desenvolvimento",
            sub: `Instalando o Android Studio, 
          Preparando o ambiente`
          },

          {
            titulo: "Conceitos Básicos",
            sub: `Criando o primeiro projeto,
          Entendendo a estrutura do projeto,
          Adição de dependências,
          Activities,
          Views,
          Resources e a classe R`
          },

          {
            titulo: "Kotlin",
            sub: `Principais recursos da linguagem,
          Null Safe,
          Data Class,
          Companion Objects`
          },

          {
            titulo: "Interface Gráfica",
            sub: `Criando um layout XML,
          Text Views,
          Edit Text,
          Button,
          Gerenciadores de layout,
          LinearLayout,
          RelativeLayout,
          ConstraintLayout`
          },
          {
            titulo: "Activities",
            sub: `Criando uma activity
          Ciclo de vida das activities
          Vinculando uma activity a um layout
          Declarando Activities no MANIFEST
          Bind de elementos de tela e suas funções
          `
          },
          {
            titulo: "Intents",
            sub: `Navegação entre telas
          Passagem de parâmetros entre telas
          `
          },
          {
            titulo: "ListView",
            sub: `Criando um listView padrão
          ViewHolder
          Adapter
          ListView Personalizado
          `
          },
          {
            titulo: "Recursos",
            sub: `Interagindo com a câmera do dispositivo
          Capturando imagens
          Interagindo com o GPS do dispositivo
          `
          },
          {
            titulo: "Banco de Dados SQLite",
            sub: `Criando um banco de dados
          Utilizando a biblioteca de persistência Room
          Manipulando dados do Banco de Dados
          
          `
          }
        ]
      },

      contato: {
        whatsApp: "(67)99290-3322",
        telefone: "(67)3387-2941",
        email: "contato@hightechcursos.com.br"
      }
    };
  }
};
</script>
