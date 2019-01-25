---
title: Convenzioni di codifica di Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: f2b1676ae959c5426af3021bbd340980115c5da6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724882"
---
# <a name="visual-basic-coding-conventions"></a>Convenzioni di codifica di Visual Basic
Microsoft sviluppa esempi e documentazione che seguono le linee guida in questo argomento. Se si seguono le stesse convenzioni di scrittura del codice, si potrebbero ottenere i vantaggi seguenti:  
  
-   Il codice avrà un aspetto coerente, in modo che chi legge possa concentrarsi meglio sul contenuto, non di layout.  
  
-   I lettori comprendono il codice più rapidamente poiché è possibile basarsi su presupposti basati sulle esperienze precedenti.  
  
-   È possibile copiare, modificare e gestire più facilmente il codice.  
  
-   Per garantire che il codice dimostra le "procedure consigliate" per Visual Basic.  
  
## <a name="naming-conventions"></a>Convenzioni di denominazione  
  
-   Per informazioni sulle convenzioni di denominazione, vedere [convenzioni di denominazione per](../../../standard/design-guidelines/naming-guidelines.md) argomento.  
  
-   Non usare "My" o "my" come parte di un nome di variabile. Questa pratica crea confusione con i `My` oggetti.  
  
-   Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattarli le linee guida.  
  
## <a name="layout-conventions"></a>Convenzioni di layout  
  
-   Inserire le tabulazioni come spazi e utilizzare i rientri con rientri di quattro spazi.  
  
-   Uso **riformatta il listato riformattazione del codice** per riformattare il codice nell'editor del codice. Per altre informazioni, vedere [opzioni, Editor di testo, base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Usare una sola istruzione per riga. Non usare il carattere separatore di riga Visual Basic (:).  
  
-   Evitare di usare il carattere di continuazione di riga esplicito "_" a favore di continuazione riga implicita, ogni volta che il linguaggio lo consente.  
  
-   Usare una sola dichiarazione per riga.  
  
-   Se **riformatta il listato riformattazione del codice** non le righe di continuazione formato automaticamente, manualmente rientro continuazione le righe di una tabulazione. Tuttavia, sempre Allinea a sinistra-elementi in un elenco.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.  
  
## <a name="commenting-conventions"></a>Convenzioni relative ai commenti  
  
-   Inserire i commenti su una riga separata anziché alla fine di una riga di codice.  
  
-   Avviare il testo di commento con una lettera maiuscola e terminarlo con un punto.  
  
-   Inserisci uno spazio tra il delimitatore di commento (') e il testo del commento.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   Non racchiudere i commenti con blocchi formattati di asterischi.  
  
## <a name="program-structure"></a>Struttura del programma  
  
-   Quando si usa la `Main` metodo, utilizzare il costrutto predefinito per le nuove applicazioni console e usare `My` per gli argomenti della riga di comando.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Linee guida della lingua  
  
### <a name="string-data-type"></a>Tipo di dati String  
  
-   Per concatenare le stringhe, usare una e commerciale (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Per accodare stringhe nei cicli, usare il <xref:System.Text.StringBuilder> oggetto.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Delegati di tipo relaxed nei gestori eventi  
 Non qualificare esplicitamente gli argomenti (Object ed EventArgs) ai gestori di eventi. Se non si usa gli argomenti dell'evento che vengono passati a un evento (ad esempio mittente come Object e come EventArgs), usare delegati di tipo relaxed e omettere gli argomenti dell'evento nel codice:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Tipi di dati non firmati  
  
-   Usare `Integer` anziché tipi senza segno, tranne quando sono necessari.  
  
### <a name="arrays"></a>Matrici  
  
-   Utilizzare la sintassi breve quando si inizializzano matrici nella riga della dichiarazione. Ad esempio, usare la sintassi seguente.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     Non utilizzare la sintassi seguente.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Inserire l'identificatore di matrici nel tipo e non sulla variabile. Ad esempio, usare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     Non utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Usare la sintassi {} quando si dichiarano e inizializzano le matrici di tipi di dati di base. Ad esempio, usare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Non utilizzare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Usare la parola chiave  
 Quando si apporta una serie di chiamate a un oggetto, è consigliabile usare il `With` (parola chiave):  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Utilizzare l'istruzione Try... Catch e le istruzioni Using quando si usa la gestione delle eccezioni  
 Non usare la proprietà `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Usare la parola chiave IsNot  
 Usare la `IsNot` parola chiave anziché `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Nuova parola chiave  
  
-   Utilizzare la creazione di istanze breve. Ad esempio, usare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     La riga precedente equivale al seguente:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Usare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Gestione di eventi  
  
-   Uso `Handles` anziché `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Usare `AddressOf`e non creare un'istanza del delegato in modo esplicito:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   Quando si definisce un evento, usare la sintassi breve e consentire al compilatore di definire il delegato:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   Non verificare se un evento è `Nothing` (null) prima di chiamare il `RaiseEvent` (metodo). `RaiseEvent` verifica la presenza di `Nothing` prima che venga generato l'evento.  
  
### <a name="using-shared-members"></a>Utilizzo di membri condivisi  
 Chiamare `Shared` membri tramite il nome della classe, non da una variabile di istanza.  
  
### <a name="use-xml-literals"></a>Usare valori letterali XML  
 Valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, query, trasformazione e caricamento). Quando si sviluppa con XML, seguire queste linee guida:  
  
-   Usare valori letterali XML per creare documenti e frammenti anziché chiamare direttamente API XML XML.  
  
-   Importare spazi dei nomi XML a livello di file o progetto in modo da sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.  
  
-   Usare le proprietà axis XML per accedere agli elementi e attributi in un documento XML.  
  
-   Utilizzare le espressioni incorporate per includere i valori e creare XML da valori esistenti anziché con chiamate all'API, ad esempio il `Add` metodo:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>Query LINQ  
  
-   Usare nomi significativi per le variabili di query:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Fornire nomi per gli elementi in una query per assicurarsi che i nomi di proprietà di tipi anonimi siano scritti correttamente in maiuscolo usando la convenzione Pascal maiuscole e minuscole:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui. Ad esempio, se la query restituisce un cliente, nome e un ID ordine, rinominarli anziché lasciarli come `Name` e `ID` nel risultato:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Usare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Allineare le clausole di query sotto la `From` istruzione:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Usare `Where` clausole prima delle altre clausole di query in modo che successive clausole di query agiscano sul set di dati filtrato:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Usare la `Join` clausola definire in modo esplicito un'operazione di join invece di usare il `Where` clausola per definire in modo implicito un'operazione di join:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md)
