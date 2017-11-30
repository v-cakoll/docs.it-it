---
title: Istruzioni in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 210637105e54244ba829dabd73feab0b43ec7c6c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="statements-in-visual-basic"></a>Istruzioni in Visual Basic
Un'istruzione in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] è un'istruzione completa. Può contenere parole chiave, operatori, variabili, costanti ed espressioni. Ogni istruzione appartiene a una delle categorie seguenti:  
  
-   **Istruzioni di dichiarazione**, quali nome di una variabile, una costante o una stored procedure e può inoltre specificare un tipo di dati.  
  
-   **Le istruzioni eseguibili**, che consentono di avviare azioni. Queste istruzioni è possono chiamare un metodo o una funzione, ed è possibile eseguire il ciclo o creare rami tramite blocchi di codice. Includono istruzioni eseguibili **istruzioni di assegnazione**, che consentono di assegnare un valore o un'espressione a una variabile o costante.  
  
 In questo argomento viene descritta ogni categoria. Inoltre, in questo argomento viene descritto come combinare più istruzioni in una singola riga e come continuare a un'istruzione su più righe.  
  
## <a name="declaration-statements"></a>Istruzioni di dichiarazione  
 Utilizzare le istruzioni di dichiarazione di denominare e definire le procedure, variabili, proprietà, matrici e costanti. Quando si dichiara un elemento di programmazione, è anche possibile definire il tipo di dati, un livello di accesso e un ambito. Per ulteriori informazioni, vedere [caratteristiche di elemento dichiarato](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 Nell'esempio seguente contiene tre dichiarazioni.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 La prima dichiarazione è il `Sub` istruzione. Con la corrispondenza `End Sub` istruzione dichiara una routine denominata `applyFormat`. Specifica inoltre che `applyFormat` è `Public`, il che significa che qualsiasi codice che può fare riferimento ad esso può chiamarlo.  
  
 La seconda dichiarazione è il `Const` istruzione che dichiara la costante `limit`, specificando il `Integer` tipo di dati e un valore pari a 33.  
  
 La terza dichiarazione è il `Dim` istruzione che dichiara la variabile `thisWidget`. Il tipo di dati è un oggetto specifico, vale a dire un oggetto creato dalla `Widget` classe. È possibile dichiarare una variabile di qualsiasi tipo di dati elementare o di qualsiasi tipo di oggetto che viene esposto nell'applicazione in uso.  
  
### <a name="initial-values"></a>Valori iniziali  
 Quando viene eseguito il codice contenente un'istruzione di dichiarazione, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] riserva la memoria necessaria per l'elemento dichiarato. Se l'elemento contiene un valore, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Inizializza il valore predefinito per il tipo di dati. Per ulteriori informazioni, vedere "Comportamento" in [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 È possibile assegnare un valore iniziale a una variabile come parte della relativa dichiarazione, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Se la variabile è una variabile oggetto, è possibile creare un'istanza della classe in modo esplicito quando si dichiara tramite il [nuovo operatore](../../../visual-basic/language-reference/operators/new-operator.md) (parola chiave), come nell'esempio riportato di seguito viene illustrato.  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Si noti che il valore iniziale specificato in un'istruzione di dichiarazione non è assegnato a una variabile, fino a quando l'esecuzione raggiunge l'istruzione di dichiarazione. Fino a quel momento, la variabile contiene il valore predefinito per il tipo di dati.  
  
## <a name="executable-statements"></a>Istruzioni eseguibili  
 Un'istruzione eseguibile esegue un'azione. È possibile chiamare una routine, un ramo a un'altra posizione nel codice, ciclo diverse istruzioni o valutare un'espressione. Un'istruzione di assegnazione è un caso speciale di un'istruzione eseguibile.  
  
 Nell'esempio seguente viene utilizzato un `If...Then...Else` struttura per l'esecuzione di diversi blocchi di codice in base al valore di una variabile di controllo. All'interno di ogni blocco di codice, un `For...Next` ciclo viene eseguito un numero di volte specificato.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 Il `If` istruzione nell'esempio precedente viene controllato il valore del parametro `clockwise`. Se il valore è `True`, chiama il `spinClockwise` metodo `aWidget`. Se il valore è `False`, chiama il `spinCounterClockwise` metodo `aWidget`. Il `If...Then...Else` struttura di controllo termina con `End If`.  
  
 Il `For...Next` ciclo all'interno di ogni blocco chiama il metodo appropriato un numero di volte uguale al valore del `revolutions` parametro.  
  
## <a name="assignment-statements"></a>Istruzioni di assegnazione  
 Istruzioni di assegnazione di eseguire operazioni di assegnazione, ovvero di ottenere il valore sul lato destro dell'operatore di assegnazione (`=`) e archiviare i dati nell'elemento a sinistra, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 Nell'esempio precedente, l'istruzione di assegnazione archivia il valore letterale 42 nella variabile `v`.  
  
### <a name="eligible-programming-elements"></a>Elementi di programmazione idonei  
 L'elemento di programmazione sul lato sinistro dell'operatore di assegnazione deve essere in grado di accettare e archiviare un valore. Ciò significa che deve essere una variabile o proprietà che non è [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), oppure deve essere un elemento di matrice. Nel contesto di un'istruzione di assegnazione, tale elemento è detto anche un *lvalue*, per "valore sinistro".  
  
 Il valore sul lato destro dell'operatore di assegnazione viene generato da un'espressione che può contenere qualsiasi combinazione di valori letterali, costanti, variabili, proprietà, gli elementi della matrice, altre espressioni o chiamate di funzione. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 Nell'esempio precedente viene aggiunto il valore contenuto nella variabile `y` al valore contenuto nella variabile `z`e quindi aggiunge il valore restituito dalla chiamata alla funzione `findResult`. Il valore totale di questa espressione viene quindi archiviato nella variabile `x`.  
  
### <a name="data-types-in-assignment-statements"></a>Tipi di dati nelle istruzioni di assegnazione  
 Oltre ai valori numerici, è possibile assegnare anche l'operatore di assegnazione `String` valori, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 È inoltre possibile assegnare `Boolean` valori, utilizzando un `Boolean` valore letterale o un `Boolean` dell'espressione, come nell'esempio seguente viene illustrato.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 Analogamente, è possibile assegnare i valori appropriati per gli elementi di programmazione del `Char`, `Date`, o `Object` tipo di dati. È inoltre possibile assegnare un'istanza dell'oggetto a un elemento dichiarato di classe da cui viene creata l'istanza.  
  
### <a name="compound-assignment-statements"></a>Istruzioni di assegnazione composta  
 *Istruzioni di assegnazione composta* prima di eseguire un'operazione su un'espressione prima di assegnarlo a un elemento di programmazione. Nell'esempio seguente viene illustrato uno di questi operatori, `+=`, che incrementa il valore della variabile sul lato sinistro dell'operatore tramite il valore dell'espressione a destra.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 Nell'esempio precedente viene aggiunto 1 al valore di `n`e quindi archivia il nuovo valore in `n`. È una sintassi abbreviata equivalente dell'istruzione seguente:  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 Una serie di operazioni di assegnazione composta può essere eseguita mediante gli operatori di questo tipo. Per un elenco di questi operatori e altre informazioni, vedere [operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 L'operatore di assegnazione di concatenazione (`&=`) è utile per l'aggiunta di una stringa alla fine della già esistenti stringhe, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>Conversioni di tipo nelle istruzioni di assegnazione  
 Il valore assegnato a una variabile, una proprietà o un elemento della matrice deve essere di un tipo di dati appropriato all'elemento di destinazione. In generale, è consigliabile generare un valore dello stesso tipo di dati a quelli dell'elemento di destinazione. Tuttavia, alcuni tipi possono essere convertiti in altri tipi durante l'assegnazione.  
  
 Per informazioni sulla conversione tra tipi di dati, vedere [conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md). In breve, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automaticamente converte un valore di un determinato tipo in qualsiasi altro tipo a cui viene ampliato. Oggetto *conversione di ampliamento* è più grande sempre ha esito positivo in fase di esecuzione e non comporta la perdita di tutti i dati. Ad esempio, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] converte un `Integer` valore `Double` quando appropriato, in quanto `Integer` ampliarsi nel tipo `Double`. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 *Conversioni di restrizione* (quelli che non sono di ampliamento) comportano rischi di errore in fase di esecuzione o di perdita di dati. È possibile eseguire una conversione di narrowing in modo esplicito utilizzando una funzione di conversione del tipo, oppure è possibile indicare al compilatore di eseguire tutte le conversioni in modo implicito impostando `Option Strict Off`. Per ulteriori informazioni, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="putting-multiple-statements-on-one-line"></a>Inserimento di più istruzioni in una sola riga  
 È possibile inserire più istruzioni in una singola riga, separata da due punti (`:`) caratteri. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Anche se in alcuni casi è utile, questa forma di sintassi rende il codice difficile da leggere e gestire. Di conseguenza, è consigliabile mantenere un'unica istruzione in una riga.  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>Continuazione di un'istruzione su più righe  
 Un'istruzione generalmente rientra in una sola riga, ma quando è troppo lungo, è possibile continuare sulla riga successiva con una sequenza di continuazione di riga, è costituito da uno spazio seguito da un carattere di sottolineatura (`_`) seguito da un ritorno a capo. Nell'esempio seguente, il `MsgBox` istruzione eseguibile continua su due righe.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>Continuazione di riga implicita  
 In molti casi, è possibile continuare un'istruzione nella riga successiva consecutiva senza utilizzare il carattere di sottolineatura (_). Nella tabella seguente sono elencati gli elementi di sintassi che continuare in modo implicito l'istruzione nella riga successiva del codice.  
  
|Elemento di sintassi|Esempio|  
|---|---|  
|Dopo una virgola (`,`).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|Dopo una parentesi aperta (`(`) o prima di una parentesi di chiusura (`)`).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|Dopo una parentesi graffa aperta (`{`) o prima della parentesi graffa di chiusura (`}`).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Per ulteriori informazioni, vedere [gli inizializzatori di oggetto: tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) o [gli inizializzatori di raccolta](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|Dopo aver aperto un espressione incorporata (`<%=`) o prima della chiusura di un'espressione incorporata (`%>`) all'interno di un valore letterale XML.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|Dopo l'operatore di concatenazione (`&`).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Per ulteriori informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Dopo gli operatori di assegnazione (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Per ulteriori informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Dopo gli operatori binari (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) all'interno di un'espressione.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Per ulteriori informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Dopo il `Is` e `IsNot` operatori.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Per ulteriori informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Dopo un carattere qualificatore di membro (`.`) e prima che il nome del membro. Tuttavia, è necessario includere un carattere di continuazione di riga (_) dopo un carattere qualificatore di membro quando si utilizza il `With` istruzione o specificando i valori nell'elenco di inizializzazione per un tipo. Si consideri l'interruzione di riga dopo l'operatore di assegnazione (ad esempio, `=`) quando si utilizza `With` istruzioni o gli elenchi di inizializzazione di oggetti.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Per ulteriori informazioni, vedere [con... Terminare con l'istruzione](../../../visual-basic/language-reference/statements/with-end-with-statement.md) o [inizializzatori di oggetto: tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|Dopo un qualificatore di proprietà axis XML (`.` o `.@` o `...`). Tuttavia, è necessario includere un carattere di continuazione di riga (_) quando si specifica un qualificatore di membro quando si utilizza il `With` (parola chiave).|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Per ulteriori informazioni, vedere [proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|Dopo un minore di-sign (<) o prima di una maggiore-segno di maggiore (`>`) quando si specifica un attributo. Anche dopo un-segno di maggiore (`>`) quando si specifica un attributo. Tuttavia, è necessario includere un carattere di continuazione di riga (_) quando si specificano gli attributi a livello di assembly o a livello di modulo.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Per ulteriori informazioni, vedere [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md).|  
|Prima e dopo gli operatori di query (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, e `Descending`). Non è possibile interrompere una linea tra le parole chiave degli operatori di query che sono costituite da più parole chiave (`Order By`, `Group Join`, `Take While`, e `Skip While`).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Per ulteriori informazioni, vedere [query](../../../visual-basic/language-reference/queries/queries.md).|  
|Dopo il `In` parola chiave in un `For Each` istruzione.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Per ulteriori informazioni, vedere [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|Dopo il `From` parola chiave in un inizializzatore di raccolta.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Per altre informazioni, vedere [Inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## <a name="adding-comments"></a>Aggiunta di commenti  
 Codice sorgente non è sempre chiara interpretazione, anche per il programmatore che lo ha scritto. Per documentare il codice, di conseguenza, la maggior parte dei programmatori sfruttare il libero commenti incorporati. I commenti nel codice possono spiegare una routine o una particolare istruzione agli utenti la lettura o l'utilizzo in un secondo momento. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Ignora i commenti durante la compilazione, e non influiscono sul codice compilato.  
  
 Le righe di commento iniziano con un apostrofo (`'`) o `REM` seguiti da uno spazio. Possono essere aggiunti in qualsiasi punto nel codice, ad eccezione all'interno di una stringa. Per aggiungere un commento a un'istruzione, inserire un apostrofo o `REM` dopo l'istruzione, seguito dal commento. I commenti possono andare anche una riga separata. L'esempio seguente illustra queste possibilità.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>Verifica degli errori di compilazione  
 Se, dopo aver digitato una riga di codice, la riga viene visualizzata una sottolineatura ondulata di colore blu (potrebbe essere visualizzato un messaggio di errore nonché), si verifica un errore di sintassi nell'istruzione. È necessario sapere qual è il problema con l'istruzione (tramite la ricerca nell'elenco attività, o passare il mouse sull'errore con il puntatore del mouse e la lettura del messaggio di errore) e correggere l'errore. Fino a quando non è stato risolto tutti gli errori di sintassi nel codice, il programma non verrà compilato correttamente.  
  
## <a name="related-sections"></a>Sezioni correlate  
  
|Termine|Definizione|  
|---|---|  
|[Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)|Vengono forniti collegamenti alle pagine di riferimento, ad esempio gli operatori di assegnazione di copertura `=`, `*=`, e `&=`.|  
|[Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Viene illustrato come combinare gli elementi con gli operatori per produrre nuovi valori.|  
|[Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Viene illustrato come suddividere una singola istruzione in più righe e come inserire più istruzioni sulla stessa riga.|  
|[Procedura: Etichettare le istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Viene illustrato come assegnare un'etichetta di una riga di codice.|
