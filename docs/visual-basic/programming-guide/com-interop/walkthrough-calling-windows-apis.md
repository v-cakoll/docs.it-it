---
title: 'Procedura dettagliata: Chiamata delle API di Windows (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: f57b5ae35bf97a04ff235d213ffad27bd015e711
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981465"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Procedura dettagliata: Chiamata delle API di Windows (Visual Basic)
Le API Windows sono librerie a collegamento dinamico (DLL) che fanno parte del sistema operativo Windows. Usarli per eseguire attività quando è difficile scrivere procedure equivalente personalizzato. Ad esempio, Windows fornisce una funzione denominata `FlashWindowEx` che consente di apportare passare alternativamente dalla chiaro e scuro sfumatura barra del titolo per un'applicazione.  
  
 Il vantaggio di usare le API di Windows nel codice è che che possano risparmiare tempo di sviluppo perché contengono molte utili funzionalità che sono già scritto e in attesa di essere utilizzato. Lo svantaggio è che le API di Windows possono essere difficili da usare e grossi se si verificano problemi.  
  
 Le API di Windows rappresentano una categoria speciale di interoperabilità. Le API di Windows non usano il codice gestito, non dispongono di librerie dei tipi e usare i tipi di dati diversi da quelli usati con Visual Studio. A causa di queste differenze, e poiché le API di Windows non sono oggetti COM, l'interoperabilità con API Windows e il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] viene eseguita usando platform invoke, o PInvoke. Platform invoke è un servizio che consente al codice gestito chiamare funzioni non gestite implementate in una DLL. Per altre informazioni, vedere [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md). È possibile usare PInvoke in Visual Basic usando il `Declare` istruzione o all'applicazione il `DllImport` attributo a una routine vuota.  
  
 Chiamate API Windows sono una parte importante di Visual Basic programming in passato, ma in genere non sono necessarie con Visual Basic .NET. Quando possibile, è necessario usare codice gestito dal [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] per eseguire attività, invece di chiamate API di Windows. Questa procedura dettagliata vengono fornite informazioni per i casi in cui tramite le API di Windows è necessaria.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Chiamate API con Declare  
 Il modo più comune per chiamare le API di Windows consiste nell'usare il `Declare` istruzione.  
  
#### <a name="to-declare-a-dll-procedure"></a>Per dichiarare una routine DLL  
  
1.  Determinare il nome della funzione da chiamare, oltre a relativi argomenti, i tipi di argomento e restituiscono valore, così come il nome e percorso della DLL che lo contiene.  
  
    > [!NOTE]
    >  Per informazioni complete sull'API di Windows, vedere la documentazione di Win32 SDK dell'API di Windows SDK di piattaforma. Per altre informazioni sulle costanti che usano le API di Windows, esaminare i file di intestazione, ad esempio incluso con il SDK della piattaforma Windows. h.  
  
2.  Aprire un nuovo progetto applicazione Windows facendo clic **New** nel **File** menu e scegliendo **progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3.  Selezionare **applicazioni Windows** dall'elenco dei modelli di progetto Visual Basic. Viene visualizzato il nuovo progetto.  
  
4.  Aggiungere il codice seguente `Declare` funzionare alla classe o modulo in cui si desidera usare la DLL:  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a>Parti dell'istruzione Declare  
 Il `Declare` istruzione include gli elementi seguenti.  
  
#### <a name="auto-modifier"></a>Modificatore Auto  
 Il `Auto` modificatore indica al runtime per convertire la stringa in base al nome di metodo in base alle regole di common language runtime (o nome di alias, se specificato).  
  
#### <a name="lib-and-alias-keywords"></a>Parole chiave lib e Alias  
 Il nome che segue il `Function` la parola chiave è il nome del programma utilizzato per accedere alla funzione importata. Può essere lo stesso come il vero nome della funzione si chiama o è possibile usare qualsiasi nome di procedura valida e quindi utilizzano il `Alias` parola chiave per specificare il nome reale della funzione che si sta chiamando.  
  
 Specificare il `Lib` (parola chiave), seguito dal nome e percorso della DLL che contiene la funzione che si sta chiamando. Non devi specificare il percorso del file che si trovano nella directory di sistema Windows.  
  
 Usare il `Alias` parola chiave se il nome della funzione chiamata non è un nome di procedure Visual Basic valido o è in conflitto con il nome di altri elementi nell'applicazione. `Alias` indica il nome reale della funzione chiamata.  
  
#### <a name="argument-and-data-type-declarations"></a>Argomenti e le dichiarazioni di tipi di dati  
 Dichiarare gli argomenti e i relativi tipi di dati. Questa parte può essere difficile poiché i tipi di dati che utilizza Windows non corrispondono ai tipi di dati di Visual Studio. Visual Basic esegue molte delle operazioni per l'utente convertendo gli argomenti ai tipi di dati compatibile, un processo denominato *marshalling*. È possibile controllare in modo esplicito la modalità di marshalling di argomenti usando il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo definito nella <xref:System.Runtime.InteropServices> dello spazio dei nomi.  
  
> [!NOTE]
>  Le versioni precedenti di Visual Basic consentono di dichiarare i parametri `As Any`, vale a dire i dati di qualsiasi dato tipo può essere utilizzato. Visual Basic richiede che si usino un tipo di dati specifico per tutti i `Declare` istruzioni.  
  
#### <a name="windows-api-constants"></a>Windows API costanti  
 Alcuni argomenti sono combinazioni di costanti. Ad esempio, il `MessageBox` API illustrato in questa procedura dettagliata accetta un argomento integer denominato `Typ` che determina come appare la finestra di messaggio. È possibile determinare il valore numerico di queste costanti esaminando il `#define` istruzioni nel file winuser. H. I valori numerici vengono in genere visualizzati in formato esadecimale, pertanto è consigliabile utilizzare una calcolatrice per aggiungerli e Converti in decimale. Ad esempio, se si desidera combinare le costanti per lo stile di punto esclamativo `MB_ICONEXCLAMATION` 0x00000030 e Sì/alcuno stile `MB_YESNO` 0x00000004, è possibile aggiungere i numeri e ottenere un risultato di 0x00000034 o 52 decimale. Anche se è possibile usare direttamente il risultato decimale, è preferibile dichiarare questi valori come costanti all'interno dell'applicazione e combinarli usando il `Or` operatore.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Per dichiarare le costanti per le chiamate API di Windows  
  
1.  Consultare la documentazione per la funzione di Windows che si sta chiamando. Determinare il nome di costanti utilizzate e il nome del file con estensione h che contiene i valori numerici per queste costanti.  
  
2.  Usare un editor di testo, ad esempio Blocco note, per visualizzare il contenuto del file di intestazione (h) e trovare i valori associati alle costanti in uso. Ad esempio, il `MessageBox` API Usa la costante `MB_ICONQUESTION` per mostrare un punto interrogativo nella finestra di messaggio. La definizione per `MB_ICONQUESTION` in winuser. H e viene visualizzato come segue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Aggiungere equivalente `Const` istruzioni per la classe o un modulo per rendere disponibili per l'applicazione le costanti. Ad esempio:  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a>Chiamare la routine DLL  
  
1.  Aggiungere un pulsante denominato `Button1` di avvio del modulo per il progetto e quindi fare doppio clic per visualizzare il relativo codice. Il gestore eventi per il pulsante viene visualizzato.  
  
2.  Aggiungere il codice per il `Click` gestore eventi per il pulsante è stato aggiunto, per chiamare la routine e fornire gli argomenti appropriati:  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3.  Eseguire il progetto premendo F5. Viene visualizzata la finestra di messaggio con entrambe **Yes** e **No** pulsanti di risposta. Fare clic su uno.  
  
#### <a name="data-marshaling"></a>Marshalling dei dati  
 Visual Basic converte automaticamente i tipi di dati dei parametri e valori restituiti per le chiamate API di Windows, ma è possibile usare il `MarshalAs` attributo specificare in modo esplicito i tipi di dati non gestiti che prevede un'API. Per altre informazioni sul marshalling di interoperabilità, vedere [marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Usare Declare e MarshalAs in una chiamata API  
  
1.  Determinare il nome della funzione da chiamare, gli argomenti, i tipi di dati e restituiscono valori.  
  
2.  Per semplificare l'accesso per il `MarshalAs` dell'attributo, aggiungere un `Imports` istruzione all'inizio del codice per la classe o modulo, come nell'esempio seguente:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3.  Aggiungere un prototipo di funzione per la funzione importata alla classe o modulo si utilizza e si applica il `MarshalAs` ai parametri dell'attributo o valore restituito. Nell'esempio seguente, una chiamata API che prevede che il tipo `void*` viene sottoposto a marshalling come `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a>Chiamate API con DllImport  
 Il `DllImport` attributo fornisce un secondo modo per chiamare le funzioni nelle DLL senza librerie dei tipi. `DllImport` è quasi equivalente all'uso di un `Declare` istruzione ma offre maggiore controllo sul modo in cui vengono chiamate le funzioni.  
  
 È possibile usare `DllImport` con l'API di Windows la maggior parte delle chiamate, purché la chiamata fa riferimento a un oggetto condiviso (detta anche *statici*) (metodo). È possibile usare i metodi che richiedono un'istanza di una classe. A differenza `Declare` istruzioni `DllImport` chiamate non è possibile utilizzare il `MarshalAs` attributo.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Per chiamare un'API di Windows usando l'attributo DllImport  
  
1.  Aprire un nuovo progetto applicazione Windows facendo clic **New** nel **File** menu e scegliendo **progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2.  Selezionare **applicazioni Windows** dall'elenco dei modelli di progetto Visual Basic. Viene visualizzato il nuovo progetto.  
  
3.  Aggiungere un pulsante denominato `Button2` al form di avvio.  
  
4.  Fare doppio clic su `Button2` per aprire la visualizzazione codice per il form.  
  
5.  Per semplificare l'accesso al `DllImport`, aggiungere un `Imports` istruzione all'inizio del codice per la classe di form di avvio:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6.  Dichiarare una funzione vuota prima la `End Class` istruzione per il modulo e il nome di funzione `MoveFile`.  
  
7.  Si applicano i `Public` e `Shared` modificatori di dichiarazione di funzione e impostare i parametri per `MoveFile` basata sugli argomenti alla funzione API Windows Usa:  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     La funzione può avere qualsiasi nome di procedura valida; il `DllImport` attributo specifica il nome nella DLL. Gestisce anche il marshalling di interoperabilità per i parametri e valori restituiti, quindi è possibile scegliere tipi di dati di Visual Studio che sono simili ai dati dei tipi utilizzati dall'API.  
  
8.  Applicare il `DllImport` attributo per la funzione vuota. Il primo parametro è il nome e il percorso della DLL che contiene la funzione che si sta chiamando. Non devi specificare il percorso del file che si trovano nella directory di sistema Windows. Il secondo parametro è un argomento denominato che specifica il nome della funzione nell'API di Windows. In questo esempio, il `DllImport` attributo impone che le chiamate a `MoveFile` deve essere inoltrato al `MoveFileW` in KERNEL32. DLL. Il `MoveFileW` metodo consente di copiare un file dal percorso `src` sul percorso `dst`.  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. Aggiungere il codice per il `Button2_Click` gestore eventi per chiamare la funzione:  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. Creare un file denominato test. txt e inserirlo nella directory C:\Tmp sul disco rigido. Se necessario, creare la directory Tmp.  
  
11. Premere F5 per avviare l’applicazione. Viene visualizzato il form principale.  
  
12. Fare clic su **Button2**. Se il file può essere spostato, viene visualizzato il messaggio "il file è stato spostato correttamente".  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)
- [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Creazione di prototipi nel codice gestito](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Marshalling di un delegato come metodo di callback](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
