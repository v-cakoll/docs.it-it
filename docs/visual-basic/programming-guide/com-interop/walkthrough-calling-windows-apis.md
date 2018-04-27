---
title: 'Procedura dettagliata: chiamata delle API di Windows (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 34bfb732e2d99b259811573a427ae66628c7fc3a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Procedura dettagliata: chiamata delle API di Windows (Visual Basic)
API Windows sono librerie a collegamento dinamico (DLL) che fanno parte del sistema operativo Windows. Usarli per eseguire attività quando è difficile scrivere routine equivalenti. Ad esempio, Windows fornisce una funzione denominata `FlashWindowEx` che consente di rendere la barra del titolo di un'applicazione alternare sfumature chiare e scure.  
  
 Il vantaggio di utilizzare le API di Windows nel codice è che è possibile salvare fase di sviluppo perché contengono molte utili funzionalità che sono già scritto e in attesa di essere utilizzato. Lo svantaggio è che le API di Windows può essere difficile e di lavoro con grossi in caso di errori.  
  
 Le API di Windows rappresentano una categoria speciale di interoperabilità. Le API di Windows non utilizzano codice gestito, non dispongono di librerie dei tipi e utilizzare i tipi di dati sono diversi da quelli utilizzati in Visual Studio. A causa di tali differenze, e poiché le API di Windows non sono oggetti COM, l'interoperabilità con le API di Windows e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] viene eseguito mediante platform invoke, PInvoke o. Platform invoke è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in una DLL. Per ulteriori informazioni, vedere [utilizzo di funzioni DLL non gestite](../../../framework/interop/consuming-unmanaged-dll-functions.md). È possibile utilizzare PInvoke in Visual Basic, utilizzando il `Declare` istruzione o l'applicazione di `DllImport` attributo a una routine vuota.  
  
 Chiamate API Windows sono una parte importante di programmazione in Visual Basic, ma in genere non sono necessarie con Visual Basic .NET. Quando possibile, è necessario utilizzare codice gestito dal [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] per eseguire attività, anziché le chiamate all'API di Windows. Questa procedura dettagliata vengono fornite informazioni per i casi in cui tramite le API di Windows è necessaria.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Chiamate API tramite Declare  
 È il modo più comune per chiamare le API di Windows utilizzando il `Declare` istruzione.  
  
#### <a name="to-declare-a-dll-procedure"></a>Per dichiarare una routine DLL  
  
1.  Determinare il nome della funzione da chiamare, più argomenti, tipi di argomenti e restituire valore, nonché il nome e percorso della DLL che lo contiene.  
  
    > [!NOTE]
    >  Per informazioni complete sulle API di Windows, vedere la documentazione di Win32 SDK nell'API di Windows SDK della piattaforma. Per ulteriori informazioni sulle costanti che utilizzano le API di Windows, esaminare i file di intestazione, ad esempio Windows. h incluso con il SDK della piattaforma.  
  
2.  Aprire un nuovo progetto applicazione Windows, fare clic su **New** sul **File** menu e quindi fare clic su **progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3.  Selezionare **applicazione Windows** dall'elenco dei modelli di progetto Visual Basic. Viene visualizzato il nuovo progetto.  
  
4.  Aggiungere il seguente `Declare` funzione in una classe o modulo in cui si desidera utilizzare la DLL:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Parti di Declare (istruzione)  
 Il `Declare` istruzione include gli elementi seguenti.  
  
#### <a name="auto-modifier"></a>Modificatore Auto  
 Il `Auto` modificatore indica al runtime di convertire la stringa in base al nome di metodo in base alle regole di common language runtime (o nome di alias se specificato).  
  
#### <a name="lib-and-alias-keywords"></a>Parole chiave lib e Alias  
 Il nome che segue il `Function` (parola chiave) è il nome del programma utilizzato per accedere alla funzione importata. Può essere lo stesso nome reale della funzione si chiama o è possibile utilizzare qualsiasi nome di routine valido e quindi utilizzano il `Alias` (parola chiave) per specificare il nome effettivo della funzione che si sta chiamando.  
  
 Specificare il `Lib` (parola chiave), seguito dal nome e percorso della DLL che contiene la funzione che si sta chiamando. Non è necessario specificare il percorso del file che si trovano nella directory di sistema di Windows.  
  
 Utilizzare il `Alias` parola chiave se il nome della funzione chiamata non è un nome di routine di Visual Basic valido o è in conflitto con il nome di altri elementi nell'applicazione. `Alias` indica il nome reale della funzione chiamata.  
  
#### <a name="argument-and-data-type-declarations"></a>Dichiarazioni di tipi di dati e di argomento  
 Dichiarare gli argomenti e i relativi tipi di dati. Può essere difficile perché i tipi di dati che utilizza Windows non corrispondono ai tipi di dati di Visual Studio. Visual Basic vengono eseguite molte delle operazioni mediante la conversione di argomenti ai tipi di dati compatibili, un processo denominato *marshalling*. È possibile controllare in modo esplicito la modalità di marshalling di argomenti utilizzando il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo definito nel <xref:System.Runtime.InteropServices> dello spazio dei nomi.  
  
> [!NOTE]
>  Le versioni precedenti di Visual Basic consentivano di dichiarare parametri `As Any`, vale a dire i dati di qualsiasi dato tipo può essere utilizzato. Visual Basic è necessario utilizzare un tipo di dati specifico per tutti `Declare` istruzioni.  
  
#### <a name="windows-api-constants"></a>Costanti di API Windows  
 Alcuni argomenti sono combinazioni di costanti. Ad esempio, il `MessageBox` API descritta in questa procedura dettagliata accetta un argomento integer denominato `Typ` che determina come appare la finestra di messaggio. È possibile determinare il valore numerico di queste costanti esaminando il `#define` istruzioni nel file winuser. H. I valori numerici vengono in genere visualizzati in formato esadecimale, pertanto è consigliabile utilizzare un calcolatore per aggiungerli e convertire in decimale. Ad esempio, se si desidera combinare le costanti per lo stile di punto esclamativo `MB_ICONEXCLAMATION` 0x00000030 e Sì/alcuno stile `MB_YESNO` 0x00000004, è possibile aggiungere i numeri e ottenere un risultato di 0x00000034 o 52 decimali. Anche se è possibile utilizzare direttamente il risultato decimale, è preferibile dichiarare questi valori come costanti nell'applicazione e di riunirle utilizzando il `Or` operatore.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Per dichiarare le costanti per le chiamate API di Windows  
  
1.  Consultare la documentazione per la funzione di Windows che si sta chiamando. Determinare il nome di costanti utilizzate e il nome del file con estensione h che contiene i valori numerici per queste costanti.  
  
2.  Utilizzare un editor di testo, ad esempio Blocco note, per visualizzare il contenuto del file di intestazione (h) e trovare i valori associati alle costanti. Ad esempio, il `MessageBox` API utilizza la costante `MB_ICONQUESTION` per visualizzare un punto interrogativo nella finestra di messaggio. La definizione per `MB_ICONQUESTION` in winuser. H e viene visualizzato come segue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Aggiungere equivalente `Const` istruzioni per la classe o il modulo per rendere disponibili per l'applicazione delle costanti. Ad esempio:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Per chiamare la routine DLL  
  
1.  Aggiungere un pulsante denominato `Button1` per l'avvio del modulo per il progetto e quindi fare doppio clic per visualizzare il codice. Il gestore dell'evento per il pulsante viene visualizzato.  
  
2.  Aggiungere codice per il `Click` gestore dell'evento del pulsante aggiunto per chiamare la routine e specificare gli argomenti appropriati:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Premere F5 per eseguire il progetto. Viene visualizzata la finestra di messaggio con entrambe **Sì** e **n** pulsanti di risposta. Fare clic su uno.  
  
#### <a name="data-marshaling"></a>Marshalling dei dati  
 Visual Basic converte automaticamente i tipi di dati dei parametri e valori restituiti per le chiamate API di Windows, ma è possibile utilizzare il `MarshalAs` attributo per specificare in modo esplicito i tipi di dati non gestiti che è prevista un'API. Per ulteriori informazioni sul marshalling di interoperabilità, vedere [marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Per utilizzare Declare e MarshalAs in una chiamata API  
  
1.  Determinare il nome della funzione da chiamare, gli argomenti, i tipi di dati, e valore restituito.  
  
2.  Per semplificare l'accesso per il `MarshalAs` attributo, aggiungere un `Imports` all'inizio del codice per la classe o modulo, come nell'esempio seguente:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Aggiungere un prototipo di funzione per la funzione importata nella classe o modulo, si utilizza e si applica il `MarshalAs` ai parametri dell'attributo o valore restituito. Nell'esempio seguente, una chiamata di API che prevede il tipo `void*` viene sottoposto a marshalling come `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>Chiamate API con DllImport  
 Il `DllImport` attributo fornisce un metodo alternativo di chiamata delle funzioni nelle DLL senza librerie dei tipi. `DllImport` è quasi equivalente all'utilizzo di un `Declare` istruzione ma offre maggiore controllo sul modo in cui le funzioni vengono chiamate.  
  
 È possibile utilizzare `DllImport` con la maggior parte delle API di Windows chiama, purché la chiamata fa riferimento a un oggetto condiviso (detto anche *statico*) metodo. Non è possibile utilizzare i metodi che richiedono un'istanza di una classe. A differenza di `Declare` istruzioni `DllImport` chiamate non è possibile utilizzare il `MarshalAs` attributo.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Per chiamare un'API di Windows utilizzando l'attributo DllImport  
  
1.  Aprire un nuovo progetto applicazione Windows, fare clic su **New** sul **File** menu e quindi fare clic su **progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2.  Selezionare **applicazione Windows** dall'elenco dei modelli di progetto Visual Basic. Viene visualizzato il nuovo progetto.  
  
3.  Aggiungere un pulsante denominato `Button2` al form di avvio.  
  
4.  Fare doppio clic su `Button2` per aprire la visualizzazione di codice per il form.  
  
5.  Per semplificare l'accesso a `DllImport`, aggiungere un `Imports` all'inizio del codice per la classe del form di avvio:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Dichiarare una funzione vuota prima di `End Class` istruzione per il modulo e il nome, la funzione `MoveFile`.  
  
7.  Applicare il `Public` e `Shared` i modificatori di dichiarazione di funzione e impostare i parametri per `MoveFile` basate sugli argomenti di funzione API di Windows utilizza:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     La funzione può avere qualsiasi nome di routine valido; il `DllImport` attributo specifica il nome della DLL. Gestisce il marshalling di interoperabilità per i parametri e valori restituiti, è possibile scegliere i tipi di dati di Visual Studio sono simili ai dati dei tipi utilizzati dall'API.  
  
8.  Applicare il `DllImport` attributo alla funzione vuota. Il primo parametro è il nome e il percorso della DLL contenente la funzione che si sta chiamando. Non è necessario specificare il percorso del file che si trovano nella directory di sistema di Windows. Il secondo parametro è un argomento denominato che specifica il nome della funzione nell'API di Windows. In questo esempio, il `DllImport` attributo impone le chiamate a `MoveFile` vengano inoltrate a `MoveFileW` in KERNEL32. DLL. Il `MoveFileW` metodo copia un file dal percorso `src` al percorso `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Aggiungere codice per il `Button2_Click` gestore eventi per chiamare la funzione:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Crea un file denominato Test.txt e lo inserisce nella directory C:\Tmp sul disco rigido. Se necessario, creare la directory Tmp.  
  
11. Premere F5 per avviare l’applicazione. Viene visualizzato il form principale.  
  
12. Fare clic su **Button2**. Se il file può essere spostato, viene visualizzato il messaggio "il file è stato spostato correttamente".  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Creazione di prototipi nel codice gestito](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [Marshalling di un delegato come metodo di callback](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
