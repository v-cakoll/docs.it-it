---
title: Convenzioni di codifica di Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 580a6e1caa78ea981b6d2be68a6e7c61e2ad55d7
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433820"
---
# <a name="visual-basic-coding-conventions"></a>Convenzioni di codifica di Visual Basic
Microsoft sviluppa esempi e documentazione che seguono le linee guida in questo argomento. Se si seguono le stesse convenzioni di codifica, è possibile ottenere i vantaggi seguenti:  
  
- Il codice avrà un aspetto coerente, in modo che i lettori possano concentrarsi meglio sul contenuto, non sul layout.  
  
- I reader comprendono il codice più rapidamente, perché possono creare presupposti in base all'esperienza precedente.  
  
- È possibile copiare, modificare e gestire il codice più facilmente.  
  
- È possibile assicurarsi che il codice consenta di illustrare "procedure consigliate" per Visual Basic.  
  
## <a name="naming-conventions"></a>Convenzioni di denominazione  
  
- Per informazioni sulle linee guida per la denominazione, vedere l'argomento [linee guida](../../../standard/design-guidelines/naming-guidelines.md) per la denominazione.  
  
- Non usare "My" o "My" come parte del nome di una variabile. Questa procedura consente di creare confusione `My` con gli oggetti.  
  
- Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattarli alle linee guida.  
  
## <a name="layout-conventions"></a>Convenzioni di layout  
  
- Inserire le schede come spazi e utilizzare i rientri intelligenti con rientri di quattro spazi.  
  
- Usare un **elenco semplice (riformattazione) del codice** per riformattare il codice nell'editor di codice. Per ulteriori informazioni, vedere [Opzioni, editor di testo, di base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
- Usare una sola istruzione per riga. Non usare il carattere separatore di riga Visual Basic (:).  
  
- Evitare di usare il carattere di continuazione di riga esplicito "_" a favore della continuazione di riga implicita laddove il linguaggio lo consente.  
  
- Usare una sola dichiarazione per riga.  
  
- Se l' **elenco (riformattazione) del codice** non formatta automaticamente le righe di continuazione, rientrare manualmente le righe di continuazione una tabulazione. Tuttavia, allinea sempre gli elementi in un elenco.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
- Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.  
  
## <a name="commenting-conventions"></a>Convenzioni relative ai commenti  
  
- Inserire i commenti su una riga separata anziché alla fine di una riga di codice.  
  
- Inizia il testo del commento con una lettera maiuscola e termina il testo del commento con un punto.  
  
- Inserire uno spazio tra il delimitatore di commento (') e il testo del commento.  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- Non racchiudere i commenti con blocchi formattati di asterischi.  
  
## <a name="program-structure"></a>Struttura del programma  
  
- Quando si utilizza il `Main` metodo, utilizzare il costrutto predefinito per le nuove applicazioni console e `My` utilizzare per gli argomenti della riga di comando.  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a>Linee guida della lingua  
  
### <a name="string-data-type"></a>Tipo di dati String  
  
- Usare l'[interpolazione di stringhe](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings) per concatenare stringhe brevi, come illustrato nel codice seguente.
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- Per accodare stringhe nei cicli, utilizzare <xref:System.Text.StringBuilder> l'oggetto.  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Delegati rilassati nei gestori eventi  
 Non qualificare in modo esplicito gli argomenti (oggetto e EventArgs) per i gestori eventi. Se non si utilizzano gli argomenti dell'evento passati a un evento, ad esempio Sender come oggetto, e come EventArgs, utilizzare delegati rilassati e lasciare gli argomenti dell'evento nel codice:  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a>Tipi di dati non firmati  
  
- Usare `Integer` anziché tipi non firmati, tranne nei casi in cui sono necessari.  
  
### <a name="arrays"></a>Matrici  
  
- Utilizzare la sintassi breve quando si inizializzano le matrici nella riga della dichiarazione. Ad esempio, usare la sintassi seguente.  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     Non utilizzare la sintassi seguente.  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- Inserire l'indicatore di matrice sul tipo, non sulla variabile. Usare, ad esempio, la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     Non usare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- Utilizzare la sintassi {} quando si dichiarano e inizializzano matrici di tipi di dati di base. Usare, ad esempio, la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     Non usare la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a>Usare la parola chiave with  
 Quando si esegue una serie di chiamate a un oggetto, provare a usare `With` la parola chiave:  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Usa il try... Intercettare e utilizzare le istruzioni quando si utilizza la gestione delle eccezioni  
 Non usare la proprietà `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Usare la parola chiave non  
 Usare la `IsNot` parola chiave invece `Not...Is Nothing`di.  
  
### <a name="new-keyword"></a>Nuova parola chiave  
  
- Usare la creazione di un'istanza breve. Usare, ad esempio, la sintassi seguente:  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     La riga precedente è equivalente alla seguente:  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- Usare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a>Gestione di eventi  
  
- `Handles` Usare`AddHandler`anziché:  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- Usare `AddressOf`e non creare un'istanza del delegato in modo esplicito:  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- Quando si definisce un evento, usare la sintassi abbreviata e consentire al compilatore di definire il delegato:  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- Non verificare se un evento è `Nothing` (null) prima di chiamare il `RaiseEvent` metodo. `RaiseEvent``Nothing` verifica prima che venga generato l'evento.  
  
### <a name="using-shared-members"></a>Uso di membri condivisi  
 Chiamare `Shared` i membri usando il nome della classe, non da una variabile di istanza.  
  
### <a name="use-xml-literals"></a>Usare valori letterali XML  
 I valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, caricamento, query e trasformazione). Quando si sviluppa con XML, attenersi alle seguenti linee guida:  
  
- Usare valori letterali XML per creare documenti e frammenti XML anziché chiamare direttamente le API XML.  
  
- Importare gli spazi dei nomi XML a livello di file o di progetto per sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.  
  
- Utilizzare le proprietà dell'asse XML per accedere a elementi e attributi in un documento XML.  
  
- Usare espressioni incorporate per includere valori e per creare codice XML da valori esistenti anziché usare chiamate API, ad `Add` esempio il metodo:  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a>Query LINQ  
  
- Usare nomi significativi per le variabili di query:  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- Fornire nomi per gli elementi in una query per assicurarsi che i nomi delle proprietà dei tipi anonimi siano correttamente in maiuscolo con la combinazione di maiuscole e minuscole Pascal:  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui. Se, ad esempio, la query restituisce un nome cliente e un ID ordine, rinominarli anziché lasciarli `Name` come `ID` e nel risultato:  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- Usare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- Allineare le clausole di `From` query nell'istruzione:  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- Usare `Where` le clausole prima di altre clausole di query in modo che le clausole di query successive funzionino sul set di dati filtrato:  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- Utilizzare la `Join` clausola per definire in modo esplicito un'operazione di join anziché `Where` utilizzare la clausola per definire in modo implicito un'operazione di join:  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md)
