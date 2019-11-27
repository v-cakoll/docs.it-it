---
title: Risoluzione dei problemi relativi all'interoperabilità
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
ms.openlocfilehash: 344c180cf0b9426898e17b45db768a337fd45beb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338677"
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Risoluzione dei problemi relativi all'interoperabilità (Visual Basic)
Quando si interagisce tra COM e il codice gestito del .NET Framework, è possibile che si verifichino uno o più dei seguenti problemi comuni.  
  
## <a name="vbconinteroperabilitymarshalinganchor1"></a>Marshalling di interoperabilità  
 In alcuni casi, potrebbe essere necessario utilizzare tipi di dati che non fanno parte del .NET Framework. Gli assembly di interoperabilità gestiscono la maggior parte del lavoro per gli oggetti COM, ma potrebbe essere necessario controllare i tipi di dati utilizzati quando gli oggetti gestiti vengono esposti a COM. Ad esempio, le strutture nelle librerie di classi devono specificare il `BStr` tipo non gestito sulle stringhe inviate a oggetti COM creati da Visual Basic 6,0 e versioni precedenti. In questi casi, è possibile usare l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> per far sì che i tipi gestiti vengano esposti come tipi non gestiti.  
  
## <a name="vbconinteroperabilitymarshalinganchor2"></a>Esportazione di stringhe a lunghezza fissa in codice non gestito  
 In Visual Basic 6,0 e versioni precedenti, le stringhe vengono esportate in oggetti COM come sequenze di byte senza un carattere di terminazione null. Per la compatibilità con altri linguaggi, Visual Basic .NET include un carattere di terminazione durante l'esportazione delle stringhe. Il modo migliore per risolvere questa incompatibilità consiste nell'esportare stringhe che non dispongono del carattere di terminazione come matrici di `Byte` o `Char`.  
  
## <a name="vbconinteroperabilitymarshalinganchor3"></a>Esportazione di gerarchie di ereditarietà  
 Le gerarchie di classi gestite vengono appiattite quando vengono esposte come oggetti COM. Se, ad esempio, si definisce una classe base con un membro e quindi si eredita la classe di base in una classe derivata esposta come oggetto COM, i client che utilizzano la classe derivata nell'oggetto COM non saranno in grado di utilizzare i membri ereditati. È possibile accedere ai membri della classe di base dagli oggetti COM solo come istanze di una classe di base e quindi solo se la classe di base viene creata anche come oggetto COM.  
  
## <a name="overloaded-methods"></a>Metodi di overload  
 Sebbene sia possibile creare metodi di overload con Visual Basic, non sono supportati da COM. Quando una classe che contiene metodi di overload viene esposta come oggetto COM, vengono generati nuovi nomi di metodo per i metodi di overload.  
  
 Si consideri, ad esempio, una classe che dispone di due overload del metodo `Synch`. Quando la classe viene esposta come oggetto COM, i nuovi nomi dei metodi generati potrebbero essere `Synch` e `Synch_2`.  
  
 La ridenominazione può causare due problemi per i consumer dell'oggetto COM.  
  
1. I client potrebbero non prevedere i nomi dei metodi generati.  
  
2. I nomi dei metodi generati nella classe esposti come oggetto COM possono essere modificati quando vengono aggiunti nuovi overload alla classe o alla relativa classe di base. Questo può causare problemi di controllo delle versioni.  
  
 Per risolvere entrambi i problemi, assegnare a ogni metodo un nome univoco, anziché usare l'overload, quando si sviluppano oggetti che verranno esposti come oggetti COM.  
  
## <a name="vbconinteroperabilitymarshalinganchor4"></a>Utilizzo di oggetti COM tramite assembly di interoperabilità  
 Gli assembly di interoperabilità vengono usati quasi come se fossero sostituzioni di codice gestito per gli oggetti COM che rappresentano. Tuttavia, poiché si tratta di wrapper e non di oggetti COM effettivi, esistono alcune differenze tra l'utilizzo degli assembly di interoperabilità e degli assembly standard. Queste aree di differenza includono l'esposizione delle classi e i tipi di dati per i parametri e i valori restituiti.  
  
## <a name="vbconinteroperabilitymarshalinganchor5"></a>Classi esposte come interfacce e classi  
 A differenza delle classi negli assembly standard, le classi COM vengono esposte negli assembly di interoperabilità sia come interfaccia sia come classe che rappresenta la classe COM. Il nome dell'interfaccia è identico a quello della classe COM. Il nome della classe di interoperabilità è identico a quello della classe COM originale, ma con la parola "class" accodata. Si supponga, ad esempio, di disporre di un progetto con un riferimento a un assembly di interoperabilità per un oggetto COM. Se la classe COM è denominata `MyComClass`, IntelliSense e il Visualizzatore oggetti mostrano un'interfaccia denominata `MyComClass` e una classe denominata `MyComClassClass`.  
  
## <a name="vbconinteroperabilitymarshalinganchor6"></a>Creazione di istanze di una classe .NET Framework  
 In genere, si crea un'istanza di una classe .NET Framework usando l'istruzione `New` con un nome di classe. La presenza di una classe COM rappresentata da un assembly di interoperabilità è un caso in cui è possibile utilizzare l'istruzione `New` con un'interfaccia. A meno che non si usi la classe COM con un'istruzione `Inherits`, è possibile usare l'interfaccia esattamente come si farebbe con una classe. Il codice seguente illustra come creare un oggetto `Command` in un progetto che contiene un riferimento all'oggetto COM della libreria Microsoft ActiveX Data Objects 2,8:  
  
 [!code-vb[VbVbalrInterop#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#20)]  
  
 Tuttavia, se si utilizza la classe COM come base per una classe derivata, è necessario utilizzare la classe di interoperabilità che rappresenta la classe COM, come nel codice seguente:  
  
 [!code-vb[VbVbalrInterop#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#21)]  
  
> [!NOTE]
> Gli assembly di interoperabilità implementano in modo implicito interfacce che rappresentano classi COM. Non provare a usare l'istruzione `Implements` per implementare queste interfacce. in caso contrario, verrà generato un errore.  
  
## <a name="vbconinteroperabilitymarshalinganchor7"></a>Tipi di dati per parametri e valori restituiti  
 A differenza dei membri degli assembly standard, i membri dell'assembly di interoperabilità possono avere tipi di dati diversi da quelli usati nella dichiarazione dell'oggetto originale. Sebbene gli assembly di interoperabilità convertano in modo implicito i tipi COM in tipi di Common Language Runtime compatibili, è necessario prestare attenzione ai tipi di dati utilizzati da entrambi i lati per evitare errori di Runtime. Ad esempio, negli oggetti COM creati in Visual Basic 6,0 e versioni precedenti, i valori di tipo `Integer` assumono il .NET Framework tipo equivalente `Short`. È consigliabile usare il Visualizzatore oggetti per esaminare le caratteristiche dei membri importati prima di usarli.  
  
## <a name="vbconinteroperabilitymarshalinganchor8"></a>Metodi COM a livello di modulo  
 La maggior parte degli oggetti COM viene utilizzata creando un'istanza di una classe COM utilizzando la parola chiave `New` e chiamando quindi i metodi dell'oggetto. Un'eccezione a questa regola riguarda gli oggetti COM che contengono `AppObj` o `GlobalMultiUse` classi COM. Tali classi sono simili ai metodi a livello di modulo in Visual Basic le classi .NET. Visual Basic 6,0 e versioni precedenti creano in modo implicito istanze di tali oggetti per la prima volta che si chiama uno dei relativi metodi. Ad esempio, in Visual Basic 6,0 è possibile aggiungere un riferimento alla libreria di oggetti Microsoft DAO 3,6 e chiamare il metodo `DBEngine` senza prima creare un'istanza:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET richiede di creare sempre istanze di oggetti COM prima di poter usare i relativi metodi. Per usare questi metodi in Visual Basic, dichiarare una variabile della classe desiderata e usare la parola chiave New per assegnare l'oggetto alla variabile oggetto. È possibile utilizzare la parola chiave `Shared` quando si desidera assicurarsi che venga creata una sola istanza della classe.  
  
 [!code-vb[VbVbalrInterop#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#23)]  
  
## <a name="vbconinteroperabilitymarshalinganchor9"></a>Errori non gestiti nei gestori eventi  
 Un problema di interoperabilità comune implica errori nei gestori eventi che gestiscono gli eventi generati dagli oggetti COM. Tali errori vengono ignorati a meno che non si verifichino in modo specifico gli errori usando le istruzioni `On Error` o `Try...Catch...Finally`. Ad esempio, l'esempio seguente è riportato da un progetto Visual Basic .NET che contiene un riferimento all'oggetto COM della libreria Microsoft ActiveX Data Objects 2,8.  
  
 [!code-vb[VbVbalrInterop#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#24)]  
  
 Questo esempio genera un errore come previsto. Tuttavia, se si prova lo stesso esempio senza il blocco `Try...Catch...Finally`, l'errore viene ignorato come se fosse stata usata l'istruzione `OnError Resume Next`. Senza la gestione degli errori, la divisione per zero non riesce automaticamente. Poiché tali errori non generano mai errori di eccezione non gestiti, è importante usare una forma di gestione delle eccezioni nei gestori eventi che gestiscono gli eventi dagli oggetti COM.  
  
### <a name="understanding-com-interop-errors"></a>Informazioni sugli errori di interoperabilità COM  
 Senza la gestione degli errori, le chiamate di interoperabilità generano spesso errori che forniscono scarse informazioni. Quando possibile, usare la gestione degli errori strutturati per fornire altre informazioni sui problemi che si verificano. Questo può essere particolarmente utile quando si esegue il debug delle applicazioni. Ad esempio:  
  
 [!code-vb[VbVbalrInterop#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#25)]  
  
 È possibile trovare informazioni quali la descrizione dell'errore, HRESULT e l'origine di errori COM esaminando il contenuto dell'oggetto eccezione.  
  
## <a name="vbconinteroperabilitymarshalinganchor10"></a>Problemi di controllo ActiveX  
 La maggior parte dei controlli ActiveX che funzionano con Visual Basic 6,0 funzionano con Visual Basic .NET senza problemi. Le eccezioni principali sono controlli contenitore o controlli che contengono visivamente altri controlli. Di seguito sono riportati alcuni esempi di controlli precedenti che non funzionano correttamente con Visual Studio:  
  
- Controllo frame Microsoft Forms 2,0  
  
- Controllo di scorrimento, noto anche come controllo di selezione  
  
- Controllo scheda Sheridan  
  
 Esistono solo alcune soluzioni alternative per i problemi di controllo ActiveX non supportati. È possibile eseguire la migrazione di controlli esistenti a Visual Studio se si è proprietari del codice sorgente originale. In caso contrario, è possibile verificare che i fornitori di software siano aggiornati. Versioni di controlli compatibili con .NET per sostituire i controlli ActiveX non supportati.  
  
## <a name="vbconinteroperabilitymarshalinganchor11"></a>Passaggio delle proprietà di sola lettura dei controlli ByRef  
 Visual Basic .NET a volte genera errori COM, ad esempio "Error 0x800A017F CTL_E_SETNOTSUPPORTED", quando si passano `ReadOnly` proprietà di alcuni controlli ActiveX meno recenti come parametri `ByRef` ad altre procedure. Chiamate di procedura analoghe da Visual Basic 6,0 non generano un errore e i parametri vengono considerati come se fossero stati passati per valore. Il messaggio di errore Visual Basic .NET indica che si sta tentando di modificare una proprietà che non dispone di una proprietà `Set` routine.  
  
 Se si ha accesso alla routine chiamata, è possibile evitare questo errore usando la parola chiave `ByVal` per dichiarare i parametri che accettano `ReadOnly` proprietà. Ad esempio:  
  
 [!code-vb[VbVbalrInterop#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#26)]  
  
 Se non si ha accesso al codice sorgente per la routine chiamata, è possibile forzare il passaggio della proprietà in base al valore aggiungendo un set aggiuntivo di parentesi quadre alla procedura chiamante. Ad esempio, in un progetto che contiene un riferimento all'oggetto COM della libreria Microsoft ActiveX Data Objects 2,8, è possibile usare:  
  
 [!code-vb[VbVbalrInterop#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#27)]  
  
## <a name="vbconinteroperabilitymarshalinganchor12"></a>Distribuzione degli assembly che espongono l'interoperabilità  
 La distribuzione di assembly che espongono interfacce COM presenta alcune esigenze specifiche. Ad esempio, un potenziale problema si verifica quando applicazioni separate fanno riferimento allo stesso assembly COM. Questa situazione è comune quando viene installata una nuova versione di un assembly e un'altra applicazione usa ancora la versione precedente dell'assembly. Se si disinstalla un assembly che condivide una DLL, è possibile renderlo involontariamente non disponibile agli altri assembly.  
  
 Per evitare questo problema, è necessario installare assembly condivisi nella global assembly cache (GAC) e usare un MergeModule per il componente. Se non è possibile installare l'applicazione nella GAC, è necessario installarla in CommonFilesFolder in una sottodirectory specifica della versione.  
  
 Gli assembly non condivisi devono trovarsi side-by-side nella directory con l'applicazione chiamante.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Global Assembly Cache](../../../framework/app-domains/gac.md)
