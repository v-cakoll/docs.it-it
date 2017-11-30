---
title: Convenzioni di codifica di Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afea862fb8783da3e69fd9828e0ded67fb81b00e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="visual-basic-coding-conventions"></a>Convenzioni di codifica di Visual Basic
Microsoft consente di sviluppare gli esempi e documentazione che seguire le istruzioni in questo argomento. Se si seguono le stesse convenzioni di codifica, si potrebbero ottenere i vantaggi seguenti:  
  
-   Il codice avrà un aspetto coerenza, in modo che chi legge possa concentrarsi meglio sul contenuto, non di layout.  
  
-   Lettori di comprendere il codice più rapidamente perché sono possibile basarsi su presupposti basati sulle esperienze precedenti.  
  
-   È possibile copiare, modificare e gestire più facilmente il codice.  
  
-   Per garantire che il codice viene illustrato "procedure consigliate" per Visual Basic.  
  
## <a name="naming-conventions"></a>Convenzioni di denominazione  
  
-   Per informazioni sulle linee guida di denominazione, vedere [convenzioni di denominazione per](../../../standard/design-guidelines/naming-guidelines.md) argomento.  
  
-   Non utilizzare "My" o "my" come parte di un nome di variabile. Questa procedura crea confusione con i `My` oggetti.  
  
-   Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattare le linee guida.  
  
## <a name="layout-conventions"></a>Convenzioni di layout  
  
-   Inserire le schede come spazi e utilizzare rientri intelligenti con rientri di quattro spazi.  
  
-   Utilizzare **listato di codice (riformattazione) di** per riformattare il codice nell'editor di codice. Per ulteriori informazioni, vedere [opzioni, Editor di testo, base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Utilizzare una sola istruzione per riga. Non utilizzare il carattere separatore di riga Visual Basic (:).  
  
-   Evitare di utilizzare il carattere di continuazione di riga esplicite "_" a favore di continuazione di riga implicita, ogni volta che ne consente la lingua.  
  
-   Utilizzare una sola dichiarazione per riga.  
  
-   Se **listato di codice (riformattazione) di** non le righe di continuazione formato automaticamente, manualmente rientro continuazione righe di una tabulazione. Tuttavia, sempre allineare a sinistra in un elenco di elementi.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.  
  
## <a name="commenting-conventions"></a>Convenzioni relative ai commenti  
  
-   Inserire i commenti su una riga separata anziché alla fine di una riga di codice.  
  
-   Avviare il testo di commento con una lettera maiuscola e testo del commento finale con un punto.  
  
-   Inserire uno spazio tra il delimitatore di commento (') e il testo del commento.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   Non racchiudere i commenti con blocchi formattati di asterischi.  
  
## <a name="program-structure"></a>Struttura del programma  
  
-   Quando si utilizza il `Main` metodo, utilizzare il costrutto predefinito per le nuove applicazioni console e `My` per gli argomenti della riga di comando.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Linee guida della lingua  
  
### <a name="string-data-type"></a>Tipo di dati String  
  
-   Per concatenare stringhe, usare una e commerciale (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Per accodare stringhe nei cicli, utilizzare il <xref:System.Text.StringBuilder> oggetto.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Delegati di tipo relaxed nei gestori eventi  
 Non qualificare in modo esplicito gli argomenti (oggetto ed EventArgs) ai gestori di eventi. Se non si utilizza gli argomenti dell'evento che vengono passati a un evento (ad esempio mittente come oggetto, e come EventArgs), utilizzare delegati di tipo relaxed e omettere gli argomenti dell'evento nel codice:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Tipi di dati non firmati  
  
-   Utilizzare `Integer` anziché tipi non firmati, tranne quando sono necessari.  
  
### <a name="arrays"></a>Matrici  
  
-   Utilizzare la sintassi breve, quando si inizializzano le matrici nella riga della dichiarazione. Ad esempio, utilizzare la sintassi seguente.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     Non utilizzare la sintassi seguente.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Il tipo e non la variabile, inserire l'identificatore di matrice. Ad esempio, utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     Non utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Quando è necessario dichiarare e inizializzare le matrici di tipi di dati di base, utilizzare la sintassi di {}. Ad esempio, utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Non utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Utilizzare la parola chiave  
 Quando si apporta una serie di chiamate a un oggetto, è consigliabile utilizzare il `With` (parola chiave):  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Utilizzare l'istruzione Try... Catch e utilizzo di istruzioni quando si utilizza Gestione delle eccezioni  
 Non utilizzare `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Utilizzare la parola chiave IsNot  
 Utilizzare il `IsNot` (parola chiave) anziché `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Nuova parola chiave  
  
-   Utilizzare la creazione di istanze breve. Ad esempio, utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     La riga precedente è equivalente a questa:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Usare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Gestione di eventi  
  
-   Utilizzare `Handles` anziché `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Utilizzare `AddressOf`e non creare un'istanza di delegato in modo esplicito:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   Quando si definisce un evento, utilizzare la sintassi breve e permettere al compilatore di definire il delegato:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   Verifica se un evento è `Nothing` (null) prima di chiamare il `RaiseEvent` metodo. `RaiseEvent`verifica la presenza di `Nothing` prima che venga generato l'evento.  
  
### <a name="using-shared-members"></a>Utilizzo di membri condivisi  
 Chiamare `Shared` membri tramite il nome della classe, non una variabile di istanza.  
  
### <a name="use-xml-literals"></a>Utilizzare valori letterali XML  
 Valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, query, trasformazione e caricamento). Quando si sviluppa con XML, attenersi alle seguenti indicazioni:  
  
-   Per creare documenti e frammenti anziché chiamare direttamente le API XML XML, utilizzare i valori letterali XML.  
  
-   Importare gli spazi dei nomi XML a livello di file o progetto in modo da sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.  
  
-   Utilizzare le proprietà axis XML per accedere agli elementi e attributi in un documento XML.  
  
-   Utilizzare le espressioni incorporate per includere i valori e creare XML da valori esistenti anziché come chiamate API di `Add` metodo:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>Query LINQ  
  
-   Utilizzare nomi significativi per le variabili di query:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Fornire i nomi per gli elementi in una query per assicurarsi che i nomi delle proprietà di tipi anonimi sono in modo corretto utilizzando la convenzione Pascal maiuscole e minuscole:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui. Ad esempio, se la query restituisce un cliente, nome e un ID ordine, rinominarli anziché lasciarli come `Name` e `ID` nel risultato:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Usare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Allineare le clausole di query sotto il `From` istruzione:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Utilizzare `Where` clausole prima delle altre clausole di query in modo che successive clausole di query agiscano su set di dati filtrati:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Utilizzare il `Join` clausola definire in modo esplicito un'operazione di join anziché il `Where` clausola per definire in modo implicito un'operazione di join:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md)
