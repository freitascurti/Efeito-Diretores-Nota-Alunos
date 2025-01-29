# Efeito-Diretores-Nota-Alunos
Efeito da forma de ingresso de diretores escolares sobre a nota dos alunos
O objetivo deste projeto é avaliar, com o software R, como a adoção do critério técnico influencia o desempenho escolar nas áreas de Português (Leitura/LP) e Matemática (MAT). A análise utiliza dados longitudinalmente estruturados de escolas que participaram da pesquisa em três anos consecutivos da PROVA BRASIL(2007, 2009 e 2011).
# Modelagem
Efeitos Fixos: Avaliação do impacto do critério técnico controlando para efeitos fixos de escola e ano.
Logit e PSM: Estimação de modelos logísticos e pareamento por escore de propensão para balanceamento das covariáveis.
Difference-in-Differences (DiD): Análise do efeito causal utilizando a metodologia DiD, tanto com quanto sem o pareamento por escore de propensão.

# Variáveis

### **1. Variáveis Escola** 
- **`id_escola`**
    
    **Descrição:** Código da escola (ID único por escola).
    
- **`year`**
    
    **Descrição:** Ano de referência dos dados (2007, 2009 ou 2011).
    
- **`cod_municipio`**
    
    **Descrição:** Código do município onde a escola está localizada.
    
- **`id_uf`**
    
    **Descrição:** Código da Unidade da Federação (estado).
    
- **`id_dependencia_adm`**
    
    **Descrição:** Dependência administrativa (tipo de gestão) da escola.
    
    - **1** = Federal
    - **2** = Estadual
    - **3** = Municipal
- **`criterio_eleicao`**
    
    **Descrição:** Indicador da forma de seleção do diretor.
    
    - **1** se a forma de seleção (`tx_21`) foi “A”, “B” ou “C” (critério técnico/eleição).
    - **0** se a forma de seleção (`tx_21`) foi “D”, “E”, “F” ou “G” (apenas indicações).

---

### 2. **Variáveis Agregadas sobre Alunos** *(provenientes de `base_agrupada`)*

- **`pct_feminino`**
    
    **Descrição:** Proporção de alunas do sexo feminino na escola, em determinado ano.
    
- **`pct_cor_preta`**
    
    **Descrição:** Proporção de alunos que se declararam de cor/raça “C” (interpretada como “preta” ou “negra”, ajuste se necessário).
    
- **`pct_computador`**
    
    **Descrição:** Proporção de alunos que declararam ter computador (e acesso à internet, se esse era o critério) em casa.
    
- **`pct_mora_mae`**
    
    **Descrição:** Proporção de alunos que moram com a mãe.
    
- **`media_escolaridade_mae`**
    
    **Descrição:** Média dos anos de estudo da mãe, categorizados e imputados conforme mapeamento.
    
- **`pct_mora_pai`**
    
    **Descrição:** Proporção de alunos que moram com o pai.
    
- **`media_escolaridade_pai`**
    
    **Descrição:** Média dos anos de estudo do pai, categorizados e imputados conforme mapeamento.
    
- **`pct_pais_incentivam`**
    
    **Descrição:** Proporção de alunos que declararam receber incentivo dos pais ou responsáveis para estudar.
    
- **`pct_trabalha_fora`**
    
    **Descrição:** Proporção de alunos que declararam trabalhar fora de casa.
    
- **`media_inicio_estudo`**
    
    **Descrição:** Média da “idade/série” em que os alunos iniciaram os estudos formais (ex.: maternal, pré-escola, 1ª série etc.).
    
- **`pct_abandono`**
    
    **Descrição:** Proporção de alunos que já haviam abandonado a escola em algum momento anterior.
    
- **`media_profic_lp`**
    
    **Descrição:** Média de proficiência em Língua Portuguesa (Leitura) dos alunos da escola, no respectivo ano.
    
- **`media_profic_mat`**
    
    **Descrição:** Média de proficiência em Matemática dos alunos da escola, no respectivo ano.
    

---

### 3. **Variáveis do Questionário do Diretor**

- **`tx_1`**: Sexo do diretor (A - Masculino, B - Feminino).
- **`tx_2`**: Idade do diretor (faixas etárias).
- **`tx_3`**: Cor/raça do diretor (A - Branco(a), B - Pardo(a), C - Preto(a), D - Amarelo(a), E - Indígena).
- **`tx_4`**: Nível máximo de escolaridade do diretor (até graduação).
- **`tx_5`**: Há quantos anos obteve o nível de escolaridade assinalado anteriormente.
- **`tx_6`**: Tipo de instituição onde cursou o ensino superior (pública, privada).
- **`tx_7`**: Natureza da instituição (faculdade isolada, centro universitário, universidade).
- **`tx_8`**: Modalidade do curso superior (presencial, semi-presencial, a distância).
- **`tx_9`**: Modalidade do curso de pós-graduação (atualização, especialização, mestrado, doutorado).
- **`tx_10`**: Área temática da pós-graduação (Gestão Escolar, Pedagógica etc.).
- **`tx_11`**: Participação em atividades de formação continuada nos últimos dois anos.
- **`tx_12`**: Carga horária da atividade de formação continuada mais relevante.
- **`tx_13`**: Utilização dos conhecimentos adquiridos na formação continuada.
- **`tx_14`**: Salário bruto do diretor (faixas salariais).
- **`tx_15`**: Renda familiar bruta do diretor (faixas salariais).
- **`tx_16`**: Exercício de outra atividade remunerada além da direção.
- **`tx_17`**: Tempo de experiência na área de educação.
- **`tx_18`**: Tempo de experiência em funções de direção.
- **`tx_19`**: Tempo como diretor na escola atual.
- **`tx_20`**: Carga horária de trabalho na escola.
- **`tx_21`**: Forma de seleção para a direção.
- **`tx_22`**: Promoção de atividades de formação continuada para docentes na escola.
- **`tx_23`**: Proporção de docentes que participaram das formações continuadas.
- **`tx_24`**: Reuniões do conselho escolar (quantidade).
- **`tx_36`**: Existência de programas de redução de abandono escolar na escola.
- **`tx_37`**: Existência de programas de redução de reprovação na escola.
- **`tx_43`**: Desenvolvimento de programas de reforço/aprendizagem para os alunos.
- **`tx_56`**: Troca de informações com outros diretores.

