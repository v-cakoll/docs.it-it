---
title: Risoluzione dei problemi relativi all'interoperabilità (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability [Visual Basic]
- interoperability, troubleshooting
- COM interop [Visual Basic], troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
ms.openlocfilehash: 65005dbbe42f52b3159c8e595972dace3064f986
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332668"
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Risoluzione dei problemi relativi all'interoperabilità (Visual Basic)
Durante l'interazione tra COM e il codice gestito del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], è possibile riscontrare uno o più dei seguenti problemi comuni.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Marshalling di interoperabilità  
 In alcuni casi, potrebbe essere necessario usare i tipi di dati che non sono in parte il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Assembly di interoperabilità di gestire la maggior parte del lavoro per gli oggetti COM, ma potrebbe essere necessario controllare i tipi di dati che vengono usati quando gli oggetti gestiti sono esposti a COM. Ad esempio, è necessario specificare le strutture nelle librerie di classi di `BStr` tipo nelle stringhe inviate agli oggetti COM creati da Visual Basic 6.0 e versioni precedenti non gestito. In questi casi, è possibile usare il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo in modo tipi gestiti da esporre come tipi non gestiti.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> Esportazione delle stringhe a lunghezza fissa a codice non gestito  
 In Visual Basic 6.0 e versioni precedenti, le stringhe vengono esportate a oggetti COM come sequenze di byte senza un carattere di terminazione null. Per garantire la compatibilità con altri linguaggi, Visual Basic .NET include un carattere di terminazione quando si esportano le stringhe. Il modo migliore per risolvere i problemi di compatibilità consiste nell'esportare che non dispongono di carattere di terminazione come matrici di stringhe `Byte` o `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> Esportazione delle gerarchie di ereditarietà  
 Classe gerarchie spianare quando esposte come oggetti COM gestita. Ad esempio, se si definisce una classe di base con un membro e quindi eredita la classe di base in una classe derivata che viene esposta come oggetto COM, i client che usano la classe derivata dell'oggetto COM non sarà in grado di usare i membri ereditati. I membri di classe di base sono accessibili dagli oggetti COM soltanto come istanze di una classe di base e quindi solo se la classe di base viene anche creata come oggetto COM.  
  
## <a name="overloaded-methods"></a>Metodi di overload  
 Sebbene sia possibile creare metodi di overload con Visual Basic, questi non sono supportati da COM. Quando una classe che contiene i metodi di overload è esposta come oggetto COM, i nuovi nomi di metodo vengono generati per i metodi di overload.  
  
 Ad esempio, si consideri una classe che ha due overload del `Synch` (metodo). Quando la classe viene esposta come oggetto COM, i nuovi nomi di metodo generato potrebbe rappresentare `Synch` e `Synch_2`.  
  
 La ridenominazione può causare due problemi per i consumer dell'oggetto COM.  
  
1.  I client potrebbero non prevedere i nomi di metodo generato.  
  
2.  I nomi di metodo generato nella classe esposta come oggetto COM possono cambiare quando vengono aggiunti nuovi overload per la classe o la relativa classe base. Ciò può provocare problemi di controllo delle versioni.  
  
 Per risolvere entrambi i problemi, assegnare ogni metodo un nome univoco, invece di usare l'overload, quando si sviluppano oggetti che saranno esposti come oggetti COM.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Uso di oggetti COM mediante assembly di interoperabilità  
 Si usano assembly di interoperabilità quasi come se fossero in sostituzione di codice gestito per gli oggetti COM che rappresentano. Tuttavia, poiché sono wrapper e gli oggetti COM non effettivi, esistono alcune differenze tra l'uso di assembly di interoperabilità e assembly standard. Le differenze includono l'esposizione di classi e tipi di dati per i parametri e valori restituiti.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> Le classi esposte come entrambe le interfacce e classi  
 A differenza delle classi negli assembly standard, le classi COM vengono esposte nell'assembly di interoperabilità come un'interfaccia sia una classe che rappresenta la classe COM. Nome dell'interfaccia è identico a quella della classe COM. Il nome della classe di interoperabilità è uguale a quello della classe COM originale, ma con la parola "Class" aggiunto. Si supponga, ad esempio, che si dispone di un progetto con un riferimento a un assembly di interoperabilità per un oggetto COM. Se la classe COM è denominata `MyComClass`, IntelliSense e il Visualizzatore Mostra un'interfaccia denominata `MyComClass` e una classe denominata `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> Creazione di istanze di classi .NET Framework  
 In genere, si crea un'istanza di un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classe usando la `New` istruzione con un nome di classe. Quando una classe COM rappresentata da un assembly di interoperabilità è un caso in cui è possibile usare il `New` istruzione con un'interfaccia. A meno che non si usa la classe COM con un `Inherits` istruzione, è possibile usare l'interfaccia esattamente come se fosse una classe. Il codice seguente viene illustrato come creare un `Command` oggetto in un progetto che contiene un riferimento all'oggetto Microsoft ActiveX Data oggetti 2.8 libreria COM:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Tuttavia, se si usa la classe COM come base per una classe derivata, è necessario utilizzare la classe di interoperabilità che rappresenta la classe COM, come nel codice seguente:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Assembly di interoperabilità in modo implicito implementano interfacce che rappresentano le classi COM. È consigliabile non usare il `Implements` determinerà l'istruzione per implementare queste interfacce o un errore.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> Tipi di dati per i parametri e valori restituiti  
 A differenza dei membri dell'assembly standard, i membri di assembly di interoperabilità abbia i tipi di dati che differiscono da quelli utilizzati nella dichiarazione dell'oggetto originale. Anche se gli assembly di interoperabilità convertono implicita dei tipi COM per tipi di common language runtime compatibile, è necessario prestare attenzione ai tipi di dati che vengono usate per entrambi i lati per evitare errori di runtime. Ad esempio, negli oggetti COM creati in Visual Basic 6.0 e versioni precedenti, i valori di tipo `Integer` presuppongono il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] tipo equivalente, `Short`. È consigliabile utilizzare il Visualizzatore oggetti per esaminare le caratteristiche dei membri importati prima di usarli.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> Metodi COM a livello di modulo  
 Vengono utilizzati quasi tutti gli oggetti COM mediante la creazione di un'istanza di una classe COM mediante la `New` (parola chiave) e quindi chiamando i metodi dell'oggetto. Un'eccezione a questa regola riguarda gli oggetti COM che contengono `AppObj` o `GlobalMultiUse` classi COM. Tali classi sono simili a metodi a livello di modulo in classi Visual Basic .NET. Visual Basic 6.0 e versioni precedenti in modo implicito creano istanze di tali oggetti è la prima volta che viene chiamato uno dei relativi metodi. In Visual Basic 6.0, ad esempio, è possibile aggiungere un riferimento per la libreria di oggetti 3.6 DAO e chiamare il `DBEngine` metodo senza dover prima creare un'istanza:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET è necessario creare istanze degli oggetti COM sempre prima di poter usare i relativi metodi. Per usare questi metodi in Visual Basic, dichiarare una variabile della classe desiderata e usare la parola chiave new per assegnare l'oggetto alla variabile di oggetto. Il `Shared` parola chiave può essere utilizzata quando si desidera assicurarsi che viene creata solo un'istanza della classe.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> Errori non gestiti nei gestori eventi  
 Un problema comune che interoperabilità comporta errori nei gestori di eventi che gestiscono gli eventi generati dagli oggetti COM. Tali errori vengono ignorati a meno che non un controllo specifico per gli errori usando `On Error` o `Try...Catch...Finally` istruzioni. Nell'esempio seguente viene ad esempio, da un progetto di Visual Basic .NET che presenta un riferimento all'oggetto Microsoft ActiveX Data oggetti 2.8 libreria COM.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 In questo esempio genera un errore nel modo previsto. Tuttavia, se si prova lo stesso esempio senza il `Try...Catch...Finally` blocco, l'errore viene ignorato perché se è stato usato il `OnError Resume Next` istruzione. Senza la gestione degli errori di divisione per zero non riuscirà automaticamente. Poiché tali errori non generano mai gli errori di eccezione non gestita, è importante usare qualche forma di gestione delle eccezioni in gestori di eventi che gestiscono gli eventi dagli oggetti COM.  
  
### <a name="understanding-com-interop-errors"></a>Informazioni sugli errori di interoperabilità COM  
 Senza la gestione degli errori, le chiamate di interoperabilità generano spesso errori che forniscono informazioni limitate. Se possibile, utilizzare gestione per fornire ulteriori informazioni sui problemi quando si verificano errori strutturata. Ciò può essere particolarmente utile quando si esegue il debug delle applicazioni. Ad esempio:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 È possibile trovare informazioni quali l'origine degli errori COM, HRESULT e la descrizione dell'errore esaminando il contenuto dell'oggetto eccezione.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> Problemi relativi al controllo ActiveX  
 La maggior parte dei controlli ActiveX che funzionano con Visual Basic 6.0 funzionano con Visual Basic .NET senza problemi. Le principali eccezioni sono controlli contenitore, o controlli visivamente contenenti altri controlli. Alcuni esempi di controlli precedenti che non funzionano correttamente con Visual Studio sono come segue:  
  
-   Controllo di Microsoft Forms 2.0 Frame  
  
-   Controllo di scorrimento, noto anche come il controllo di selezione  
  
-   Schede Sheridan  
  
 Sono disponibili solo alcune soluzioni alternative per problemi di controlli ActiveX non supportati. Se si è proprietari del codice sorgente originale, è possibile migrare i controlli esistenti a Visual Studio. In caso contrario, è possibile controllare con fornitori di software per l'aggiornamento. Le versioni compatibili di NET dei controlli da sostituire non supportati controlli ActiveX.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> Passaggio delle proprietà di sola lettura ByRef typu ByRef controlli  
 Visual Basic .NET a volte genera errori COM, ad esempio, "Errore 0x800A017F CTL_E_SETNOTSUPPORTED", quando si passano `ReadOnly` delle proprietà di alcuni controlli ActiveX precedente come `ByRef` parametri alle altre procedure. Chiamate di procedure simili da Visual Basic 6.0 non generano un errore e i parametri vengono considerati come se li si passati per valore. Il messaggio di errore di Visual Basic .NET indica che si sta tentando di modificare una proprietà che non dispone di una proprietà `Set` procedure.  
  
 Se si ha accesso per la routine chiamata, è possibile impedire questo errore tramite il `ByVal` parola chiave per dichiarare i parametri che accettano `ReadOnly` proprietà. Ad esempio:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Se non si ha accesso al codice sorgente per la routine chiamata, è possibile forzare la proprietà può essere passato per valore mediante l'aggiunta di un set aggiuntivo di parentesi quadre intorno alla routine chiamante. Ad esempio, in un progetto che contiene un riferimento all'oggetto COM della libreria di Microsoft ActiveX Data oggetti 2.8, è possibile usare:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Distribuzione di assembly che espongono l'interoperabilità  
 Distribuzione di assembly che espongono interfacce COM presenta alcune sfide univoche. Ad esempio, un potenziale problema si verifica quando applicazioni separate che fa riferimento allo stesso assembly COM. Questa situazione è comune quando si installa una nuova versione di un assembly e un'altra applicazione utilizza ancora la versione precedente dell'assembly. Se si disinstalla un assembly che condivide una DLL, è possibile involontariamente renderlo disponibile per gli altri assembly.  
  
 Per evitare questo problema, è necessario installare gli assembly condivisi alla Global Assembly Cache (GAC) e usare un MergeModule per il componente. Se non è possibile installare l'applicazione nella Global Assembly Cache, questo servizio deve essere installato in CommonFilesFolder in una sottodirectory specifica della versione.  
  
 Gli assembly che non sono condivisi devono trovarsi side-by-side nella stessa directory dell'applicazione chiamante.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Global Assembly Cache](../../../framework/app-domains/gac.md)
