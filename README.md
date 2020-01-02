<!--
2º Projeto de Linguagens de Programação II 2019/2020 (c) by Nuno Fachada

2º Projeto de Linguagens de Programação II 2019/2020 is licensed under a
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-nc-sa/4.0/>.
-->

# 2º Projeto de Linguagens de Programação II 2019/2020

## Descrição do problema

Os grupos devem implementar um jogo em C# \[[1][ref1],[2][ref2]\] usando os
principais *design patterns* para jogos \[[3][ref3]\], bem como *design
patterns* mais gerais \[[4][ref4]\] quando apropriado, tendo sempre em conta
os diferentes princípios de design de classes, como por exemplo os princípios
[SOLID].

### O jogo a desenvolver

O jogo deve ser desenvolvido em modo de consola, mais especificamente como uma
aplicação .NET Core multi-plataforma, devendo também funcionar e ser testado em
Mac e/ou Linux (devem ser evitadas classes ou métodos específicos para Windows).
O jogo em si deve ser jogável em tempo real, ou seja, não deve ser *turn-based*.
Aceitam-se propostas, mas ficam algumas sugestões:

* [Tetris]
* [Space Invaders]
* [Pong]
* [Asteroids]
* [Snake]
* [Frogger]
* [Breakout]
* [Moon Buggy]
* [Tron]
* [Pac-Man]
* [Spacewar!]

Cada grupo deve implementar um jogo diferente, sendo que os primeiros a
indicar a escolha via email ou Moodle terão direito a desenvolver o respetivo
jogo. A lista de jogos atribuídas será colocada e atualizada no Moodle. Alguns
jogos poderão ter dificuldades específicas, pelo que se tiverem dúvidas entrem
em contacto para analisarmos a situação.

Não é necessário (e na maior parte dos casos, nem sequer é possível) que o jogo
seja uma réplica exata do original, bastando implementar as mecânicas básicas,
ser jogável e ter algum tipo de pontuação. É também necessário indicar, antes
do jogo começar, as regras e controlos do mesmo. Naturalmente serão bonificadas
soluções mais completas, com menu, lista de *high scores* persistente entre
jogos, vários níveis, animações dinâmicas, etc. Não é necessário o uso de cores
na consola nem de som.

<a name="reqmin"></a>

### Requisitos técnicos mínimos

O jogo deve no mínimo fazer uso das seguintes técnicas:

* Ter como base de implementação o [Game Loop] e o [Update Method]. O
  [Component Pattern] poderá ser essencial para uma boa organização do código.
* Ter (pelo menos) duas *threads*: a *thread* principal do jogo (que executa
  o *game loop*) e uma *thread* para ler *input* do utilizador.

O jogo deve ainda:

* Implementar as mecânicas base do jogo original.
* Ser jogável e ter algum tipo de pontuação.
* Ter algum tipo de ecrã inicial ou opção no menu onde sejam explicadas as
  regras e indicados os controlos do jogo.

<a name="orgclasses"></a>

### Organização do projeto e estrutura de classes

O projeto deve estar devidamente organizado, fazendo uso de classes, `struct`s
e/ou enumerações, consoante seja mais apropriado. Cada tipo (i.e., classe,
`struct` ou enumeração) deve ser colocado num ficheiro com o mesmo nome. Por
exemplo, uma classe chamada `Game` deve ser colocada no ficheiro `Game.cs`. Por
sua vez, a escolha da coleções e *design patterns* também deve ser adequada a
cada situação. Serão previligiadas soluções que tenham em consideração bons
princípios de design de classes, como é o caso dos princípios [SOLID]. Estes
*patterns* e princípios devem ser balanceados com o princípio [KISS], crucial
no desenvolvimento de qualquer sistema.

<a name="objetivos"></a>

## Objetivos e critério de avaliação

Este projeto tem os seguintes objetivos:

* **O1** - Projeto deve cumprir os [requisitos mínimos](#reqmin).
* **O2** - Projeto e código bem organizados, nomeadamente:
  * Estrutura de classes bem pensada (ver secção [Organização do projeto e
    estrutura de classes](#orgclasses)).
  * Código devidamente comentado e indentado.
  * Inexistência de código "morto", que não faz nada, como por exemplo
    variáveis, propriedades ou métodos nunca usados.
  * Projeto compila e executa sem erros e/ou *warnings*.
* **O3** - Projeto adequadamente documentado. Documentação deve ser feita com
  [comentários de documentação XML][XML], e a documentação (gerada em formato
  HTML ou CHM com [Doxygen][], [Sandcastle][] ou ferramenta similar
  [\[5\]][ref5]) deve estar incluída no ZIP do projeto, mas **não** integrada
  no repositório Git.
* **O4** - Repositório Git deve refletir boa utilização do mesmo, com
  *commits* de todos os elementos do grupo e mensagens de *commit* que sigam
  as melhores práticas para o efeito (como indicado
  [aqui](https://chris.beams.io/posts/git-commit/),
  [aqui](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53),
  [aqui](https://github.com/erlang/otp/wiki/writing-good-commit-messages) e
  [aqui](https://stackoverflow.com/questions/2290016/git-commit-messages-50-72-formatting)).
  Quaisquer *assets* binários, tais como imagens, devem ser integrados
  no repositório em modo Git LFS.
* **O5** - Relatório em formato [Markdown] (ficheiro `README.md`),
  organizado da seguinte forma:
  * Título do projeto.
  * Autoria:
    * Nome dos autores (primeiro e último) e respetivos números de aluno.
    * Informação de quem fez o quê no projeto. Esta informação é
      **obrigatória** e deve refletir os *commits* feitos no Git.
    * Indicação do repositório público Git utilizado. Esta indicação é
      opcional, pois podem preferir desenvolver o projeto num repositório
      privado.
  * Arquitetura da solução:
    * Descrição da solução, com breve explicação de como o programa foi
      organizado, indicação dos *design patterns* utilizados e a razão do
      seu uso, bem como dos algoritmos implementados (e.g., para deteção
      de colisões, cálculo de ângulos e trajetórias, etc).
    * Um diagrama UML de classes simples (i.e., sem indicação dos
      membros da classe) descrevendo a estrutura de classes.
    * Um fluxograma mostrando o funcionamento do programa.
  * Referências, incluindo trocas de ideias com colegas, código aberto
    reutilizado (e.g., do StackOverflow) e bibliotecas de terceiros
    utilizadas. Devem ser o mais detalhados possível.
  * **Nota:** o relatório deve ser simples e breve, com informação mínima e
    suficiente para que seja possível ter uma boa ideia do que foi feito.
    Atenção aos erros ortográficos e à correta formatação [Markdown], pois
    ambos serão tidos em conta na nota final.

O projeto tem um peso de 3 valores na nota final da disciplina e será avaliado
de forma qualitativa. Isto significa que todos os objetivos têm de ser
parcialmente ou totalmente cumpridos. A cada objetivo, O1 a O5, será atribuída
uma nota entre 0 e 1. A nota do projeto será dada pela seguinte fórmula:

*N = 3 x O1 x O2 x O3 x O4 x O5 x D*

Em que *D* corresponde à nota da discussão e percentagem equitativa de
realização do projeto, também entre 0 e 1. Isto significa que se os alunos
ignorarem completamente um dos objetivos, não tenham feito nada no projeto ou
não comparecerem na discussão, a nota final será zero.

## Entrega

O projeto deve ser entregue por **grupos de 2 a 3 alunos** via Moodle até às
23h de 7 de janeiro de 2020. Deve ser submetido um ficheiro `zip` com a
solução completa do projeto, nomeadamente:

* Pasta escondida `.git` com o repositório Git local do projeto.
* Documentação HTML ou CHM gerada com [Doxygen], [Sandcastle] ou ferramenta
  similar.
* Ficheiro `README.md` contendo o relatório do projeto em formato [Markdown].
* Ficheiros de imagens, contendo o diagrama UML de classes, o fluxograma, e
  outras figuras que considerem úteis. Estes ficheiros devem ser incluídos no
  repositório em modo Git LFS.

## Honestidade académica

Nesta disciplina, espera-se que cada aluno siga os mais altos padrões de
honestidade académica. Isto significa que cada ideia que não seja do
aluno deve ser claramente indicada, com devida referência ao respetivo
autor. O não cumprimento desta regra constitui plágio.

O plágio inclui a utilização de ideias, código ou conjuntos de soluções
de outros alunos ou indivíduos, ou quaisquer outras fontes para além
dos textos de apoio à disciplina, sem dar o respetivo crédito a essas
fontes. Os alunos são encorajados a discutir os problemas com outros
alunos e devem mencionar essa discussão quando submetem os projetos.
Essa menção **não** influenciará a nota. Os alunos não deverão, no
entanto, copiar códigos, documentação e relatórios de outros alunos, ou dar os
seus próprios códigos, documentação e relatórios a outros em qualquer
circunstância. De facto, não devem sequer deixar códigos, documentação e
relatórios em computadores de uso partilhado.

Nesta disciplina, a desonestidade académica é considerada fraude, com
todas as consequências legais que daí advêm. Qualquer fraude terá como
consequência imediata a anulação dos projetos de todos os alunos envolvidos
(incluindo os que possibilitaram a ocorrência). Qualquer suspeita de
desonestidade académica será relatada aos órgãos superiores da escola
para possível instauração de um processo disciplinar. Este poderá
resultar em reprovação à disciplina, reprovação de ano ou mesmo suspensão
temporária ou definitiva da ULHT.

*Texto adaptado da disciplina de [Algoritmos e
Estruturas de Dados][aed] do [Instituto Superior Técnico][ist]*

## Referências

*   <a name="ref1">\[1\]</a> Whitaker, R. B. (2016). **The C# Player's Guide**
    (3rd Edition). Starbound Software.
*   <a name="ref2">\[2\]</a> Albahari, J. (2017). **C# 7.0 in a Nutshell**.
    O’Reilly Media.
*   <a name="ref3">\[3\]</a> Nystrom, R. (2014). **Game Programming Patterns**.
    Genever Benning. Retrieved from <http://gameprogrammingpatterns.com/>.
*   <a name="ref4">\[4\]</a> Freeman, E., Robson, E., Bates, B., & Sierra, K.
    (2004). **Head First Design Patterns**. O'Reilly Media.
*   <a name="ref5">\[5\]</a> Dorsey, T. (2017). **Doing Visual Studio and .NET
    Code Documentation Right**. Visual Studio Magazine. Retrieved from
    <https://visualstudiomagazine.com/articles/2017/02/21/vs-dotnet-code-documentation-tools-roundup.aspx>.

## Licenças

Este enunciado é disponibilizado através da licença [CC BY-NC-SA 4.0][].

## Metadados

*   Autor: [Nuno Fachada]
*   Curso:  [Licenciatura em Videojogos][lamv]
*   Instituição: [Universidade Lusófona de Humanidades e Tecnologias][ULHT]

[ref1]:#ref1
[ref2]:#ref2
[ref3]:#ref3
[ref4]:#ref4
[ref5]:#ref5
[CC BY-NC-SA 4.0]:https://creativecommons.org/licenses/by-nc-sa/4.0/
[lamv]:https://www.ulusofona.pt/licenciatura/videojogos
[Nuno Fachada]:https://github.com/fakenmc
[ULHT]:https://www.ulusofona.pt/
[aed]:https://fenix.tecnico.ulisboa.pt/disciplinas/AED-2/2009-2010/2-semestre/honestidade-academica
[ist]:https://tecnico.ulisboa.pt/pt/
[Markdown]:https://guides.github.com/features/mastering-markdown/
[Doxygen]:https://www.stack.nl/~dimitri/doxygen/
[Sandcastle]:https://github.com/EWSoftware/SHFB
[KISS]:https://en.wikipedia.org/wiki/KISS_principle
[XML]:https://docs.microsoft.com/dotnet/csharp/codedoc
[SOLID]:https://en.wikipedia.org/wiki/SOLID
[Snake]:https://en.wikipedia.org/wiki/Snake_(video_game_genre)
[Frogger]:https://en.wikipedia.org/wiki/Frogger
[Breakout]:https://en.wikipedia.org/wiki/Breakout_(video_game)
[Moon buggy]:https://www.seehuhn.de/pages/moon-buggy
[Tron]:https://en.wikipedia.org/wiki/Tron_(video_game)
[Pac-Man]:https://en.wikipedia.org/wiki/Pac-Man
[Asteroids]:https://en.wikipedia.org/wiki/Asteroids_(video_game)
[Pong]:https://en.wikipedia.org/wiki/Pong
[Tetris]:https://en.wikipedia.org/wiki/Tetris
[Space Invaders]:https://en.wikipedia.org/wiki/Space_Invaders
[Spacewar!]:https://en.wikipedia.org/wiki/Spacewar!
[Game Loop]:http://gameprogrammingpatterns.com/game-loop.html
[Update Method]:http://gameprogrammingpatterns.com/update-method.html
[Component Pattern]:https://gameprogrammingpatterns.com/component.html
