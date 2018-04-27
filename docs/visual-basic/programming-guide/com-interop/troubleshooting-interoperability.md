---
title: Risoluzione dei problemi relativi all'interoperabilità (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3ff175a0f8d152febf2d50c294d401b12285fc7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Risoluzione dei problemi relativi all'interoperabilità (Visual Basic)
Durante l'interazione tra COM e il codice gestito del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], si potrebbe verificarsi uno o più dei seguenti problemi comuni.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Marshalling di interoperabilità  
 In alcuni casi, potrebbe essere necessario utilizzare i tipi di dati che non sono in parte il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Gli assembly di interoperabilità gestiscono la maggior parte del lavoro per gli oggetti COM, ma potrebbe essere necessario controllare i tipi di dati che vengono utilizzati quando gli oggetti gestiti esposti a COM. Ad esempio, è necessario specificare le strutture in librerie di classi di `BStr` tipo nelle stringhe inviate a oggetti COM creati mediante Visual Basic 6.0 e versioni precedenti non gestito. In questi casi, è possibile utilizzare il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo in modo da esporre come tipi non gestiti i tipi gestiti.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> Esportazione delle stringhe di lunghezza fissa a codice non gestito  
 In Visual Basic 6.0 e versioni precedenti, le stringhe vengono esportate a oggetti COM come sequenze di byte senza un carattere di terminazione null. Per garantire la compatibilità con altri linguaggi, Visual Basic .NET include un carattere di terminazione durante l'esportazione delle stringhe. È il modo migliore per risolvere questo problema di incompatibilità per esportare le stringhe senza carattere di terminazione come matrici di `Byte` o `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> Esportazione di gerarchie di ereditarietà  
 Gerarchie spianare quando esposti come oggetti COM di classe gestita. Ad esempio, se si definisce una classe base con un membro e quindi ereditare la classe base in una classe derivata che viene esposto come un oggetto COM, i client che usano la classe derivata dell'oggetto COM non sarà in grado di utilizzare i membri ereditati. Membri della classe base è possibile accedere dagli oggetti COM solo come istanze di una classe base, quindi solo se la classe di base viene inoltre creata come un oggetto COM.  
  
## <a name="overloaded-methods"></a>Metodi di overload  
 Sebbene sia possibile creare metodi di overload con Visual Basic, non sono supportate da COM. Quando una classe che contiene i metodi di overload è esposta come un oggetto COM, vengono generati nuovi nomi per i metodi di overload.  
  
 Ad esempio, si consideri una classe che dispone di due overload di `Synch` metodo. Quando la classe viene esposta come un oggetto COM, i nuovi nomi di metodo generato potrebbe essere `Synch` e `Synch_2`.  
  
 La ridenominazione può causare due problemi per i consumer dell'oggetto COM.  
  
1.  I client potrebbero non prevedere i nomi di metodo generato.  
  
2.  I nomi di metodo generato nella classe esposta come oggetto COM possono cambiare quando vengono aggiunti nuovi overload per la classe o la relativa classe base. Ciò può provocare problemi di controllo delle versioni.  
  
 Per risolvere entrambi i problemi, assegnare a ogni metodo un nome univoco, anziché utilizzare l'overload, quando si sviluppano oggetti che saranno esposti come oggetti COM.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Utilizzo di oggetti COM tramite assembly di interoperabilità  
 Utilizzare assembly di interoperabilità quasi come se fossero in sostituzione di codice gestito per gli oggetti COM che rappresentano. Tuttavia, poiché si tratta di wrapper e gli oggetti COM non effettivi, esistono alcune differenze tra l'utilizzo di assembly di interoperabilità e gli assembly standard. Le differenze includono l'esposizione di classi e tipi di dati per i parametri e valori restituiti.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> Classi esposte come entrambe le interfacce e classi  
 A differenza delle classi negli assembly standard, vengono esposte le classi COM negli assembly di interoperabilità come un'interfaccia e una classe che rappresenta la classe COM. Il nome dell'interfaccia è identico a quello della classe COM. Il nome della classe di interoperabilità è uguale a quello della classe COM originale, ma con la parola "Class" aggiunto. Si supponga, ad esempio, che si dispone di un progetto con un riferimento a un assembly di interoperabilità per un oggetto COM. Se la classe COM è denominata `MyComClass`, IntelliSense e il Visualizzatore Mostra un'interfaccia denominata `MyComClass` e una classe denominata `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> Creazione di istanze di classi .NET Framework  
 In genere viene creata un'istanza di un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] usando il `New` istruzione con un nome di classe. Disporre di una classe COM rappresentata da un assembly di interoperabilità è un caso in cui è possibile utilizzare il `New` istruzione con un'interfaccia. A meno che non si utilizza la classe COM con un `Inherits` istruzione, è possibile utilizzare l'interfaccia come se fosse una classe. Il codice seguente viene illustrato come creare un `Command` oggetto in un progetto che contiene un riferimento all'oggetto Microsoft ActiveX Data oggetti 2.8 libreria COM:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Tuttavia, se si utilizza la classe COM come base per una classe derivata, è necessario utilizzare la classe di interoperabilità che rappresenta la classe COM, come illustrato nel codice seguente:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Assembly di interoperabilità in modo implicito implementano interfacce che rappresentano classi COM. Non tentare di utilizzare il `Implements` comporterà l'istruzione per implementare queste interfacce o un errore.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> Tipi di dati per i parametri e valori restituiti  
 A differenza dei membri dell'assembly standard, i membri di assembly di interoperabilità possono includere tipi di dati che differiscono da quelle usate nella dichiarazione dell'oggetto originale. Anche se gli assembly di interoperabilità convertono implicita dei tipi COM in tipi di common language runtime compatibile, è necessario prestare attenzione ai tipi di dati che vengono utilizzati da entrambi i lati per evitare errori di runtime. Ad esempio, negli oggetti COM creati in Visual Basic 6.0 e versioni precedenti, i valori di tipo `Integer` presuppongono il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] tipo equivalente, `Short`. È consigliabile utilizzare il Visualizzatore oggetti per esaminare le caratteristiche dei membri importati prima di utilizzarli.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> Metodi COM a livello di modulo  
 La maggior parte degli oggetti COM vengono utilizzati creando un'istanza di una classe COM utilizzando il `New` (parola chiave) e quindi chiamando i metodi dell'oggetto. Un'eccezione a questa regola riguarda gli oggetti COM che contengono `AppObj` o `GlobalMultiUse` classi COM. Tali classi assomigliano ai metodi a livello di modulo nelle classi di Visual Basic .NET. Visual Basic 6.0 e versioni precedenti in modo implicito creano istanze di tali oggetti è la prima volta che si chiama uno dei relativi metodi. In Visual Basic 6.0, ad esempio, è possibile aggiungere un riferimento alla libreria di oggetti di Microsoft DAO 3.6 e chiamare il `DBEngine` metodo senza prima creare un'istanza:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET è necessario creare istanze di oggetti COM sempre prima di poter usare i relativi metodi. Per utilizzare questi metodi in Visual Basic, dichiarare una variabile della classe desiderata e utilizzare la parola chiave new per assegnare l'oggetto per la variabile oggetto. Il `Shared` (parola chiave) utilizzabile quando si desidera assicurarsi che solo un'istanza della classe viene creata.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> Errori non gestiti nei gestori eventi  
 Un problema di interoperabilità comune prevede errori nei gestori di eventi che gestiscono gli eventi generati da oggetti COM. Tali errori vengono ignorati a meno che non un controllo specifico per gli errori usando `On Error` o `Try...Catch...Finally` istruzioni. Nell'esempio seguente, ad esempio, è da un progetto di Visual Basic .NET che include un riferimento all'oggetto Microsoft ActiveX Data oggetti 2.8 libreria COM.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 In questo esempio genera un errore, come previsto. Tuttavia, se si tenta l'esempio precedente senza il `Try...Catch...Finally` blocco, l'errore viene ignorato se è stato utilizzato il `OnError Resume Next` istruzione. Senza la gestione degli errori, la divisione per zero non riuscirà automaticamente. Poiché tali errori non generano mai un'eccezione non gestita errori, è importante utilizzare una forma di gestione delle eccezioni nei gestori di eventi che gestiscono gli eventi dagli oggetti COM.  
  
### <a name="understanding-com-interop-errors"></a>Informazioni sugli errori di interoperabilità COM  
 Senza la gestione degli errori, le chiamate di interoperabilità spesso generano errori che forniscono informazioni limitate. Se possibile, utilizzare gestione per fornire ulteriori informazioni sui problemi quando si verificano strutturata. Può essere particolarmente utile quando si esegue il debug di applicazioni. Ad esempio:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 È possibile trovare informazioni quali la descrizione dell'errore, HRESULT e l'origine degli errori COM esaminando il contenuto dell'oggetto eccezione.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> Problemi relativi al controllo ActiveX  
 La maggior parte dei controlli ActiveX che funzionano con Visual Basic 6.0 funzionano con Visual Basic .NET senza problemi. Le eccezioni principali sono controlli contenitore o i controlli contenenti visivamente altri controlli. Alcuni esempi di controlli precedenti che non funzionano correttamente con [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] sono i seguenti:  
  
-   Controllo Microsoft Forms 2.0 Frame  
  
-   Controllo di scorrimento, noto anche come il controllo di selezione  
  
-   Schede Sheridan  
  
 Sono disponibili solo alcune soluzioni per problemi di controlli ActiveX non supportati. È possibile migrare i controlli esistenti a [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] se si è proprietari del codice sorgente originale. In caso contrario, è possibile controllare con fornitori di software per l'aggiornamento. Versioni compatibili con NET dei controlli da sostituire non supportati controlli ActiveX.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> Passaggio di proprietà di sola lettura di controlli ByRef  
 Visual Basic .NET talvolta genera errori COM, ad esempio, "Error 0x800A017F CTL_E_SETNOTSUPPORTED" quando si passano `ReadOnly` le proprietà di alcuni controlli ActiveX meno recenti come `ByRef` parametri per le altre routine. Chiamate di routine simili da Visual Basic 6.0 non generano un errore e i parametri vengono considerati come se passati per valore. Il messaggio di errore di Visual Basic .NET indica che si sta tentando di modificare una proprietà che non dispone di una proprietà `Set` stored procedure.  
  
 Se si dispone dell'accesso per la routine chiamata, è possibile impedire questo errore utilizzando il `ByVal` (parola chiave) per dichiarare i parametri che accettano `ReadOnly` proprietà. Ad esempio:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Se non si dispone di accesso al codice sorgente per la routine chiamata, è possibile forzare la proprietà deve essere passato dal valore tramite l'aggiunta di un set aggiuntivo di parentesi per racchiudere la chiamata di procedura. In un progetto che contiene un riferimento all'oggetto Microsoft ActiveX Data oggetti 2.8 libreria COM, ad esempio, è possibile utilizzare:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Distribuzione di assembly che espongono interoperabilità  
 Distribuzione di assembly che espongono le interfacce COM presenta alcune difficoltà specifiche. Ad esempio, un potenziale problema si verifica quando le diverse applicazioni fanno riferimento allo stesso assembly COM. Questa situazione è comune quando è installata una nuova versione di un assembly e un'altra applicazione utilizza ancora la versione precedente dell'assembly. Se si disinstalla un assembly che condivide una DLL, è possibile involontariamente renderlo disponibile agli altri assembly.  
  
 Per evitare questo problema, installare gli assembly condivisi per Global Assembly Cache (GAC) e utilizzare un modulo unione per il componente. Se è possibile installare l'applicazione nella GAC, deve essere installato in CommonFilesFolder in una sottodirectory specifica della versione.  
  
 Gli assembly condivisi non devono trovarsi side-by-side nella directory dell'applicazione chiamante.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Global Assembly Cache](../../../framework/app-domains/gac.md)
