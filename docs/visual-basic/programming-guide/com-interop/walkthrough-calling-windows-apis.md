---
title: 'Procedura dettagliata: Chiamata delle API di Windows'
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
ms.openlocfilehash: c7b84a3bb12329ae235e5ea03dc5e86f921112c4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396753"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Procedura dettagliata: chiamata delle API di Windows (Visual Basic)
Le API di Windows sono librerie a collegamento dinamico (dll) che fanno parte del sistema operativo Windows. Vengono usati per eseguire attività quando è difficile scrivere procedure equivalenti personalizzate. Windows, ad esempio, fornisce una funzione denominata `FlashWindowEx` che consente di fare in modo che la barra del titolo di un'applicazione venga alternata tra le tonalità chiaro e scuro.  
  
 Il vantaggio di usare le API di Windows nel codice è che consentono di risparmiare tempo di sviluppo perché contengono dozzine di funzioni utili già scritte e in attesa di essere usate. Lo svantaggio è che le API di Windows possono essere difficili da utilizzare e non perdonare quando si verificano problemi.  
  
 Le API di Windows rappresentano una categoria speciale di interoperabilità. Le API Windows non utilizzano codice gestito, non dispongono di librerie dei tipi predefinite e utilizzano tipi di dati diversi da quelli utilizzati con Visual Studio. A causa di queste differenze, e poiché le API di Windows non sono oggetti COM, l'interoperabilità con le API Windows e la .NET Framework viene eseguita utilizzando platform invoke o PInvoke. Platform Invoke è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in dll. Per ulteriori informazioni, vedere [utilizzo di funzioni dll non gestite](../../../framework/interop/consuming-unmanaged-dll-functions.md). È possibile utilizzare PInvoke in Visual Basic utilizzando l' `Declare` istruzione o applicando l' `DllImport` attributo a una routine vuota.  
  
 Le chiamate all'API di Windows rappresentano una parte importante della programmazione Visual Basic in passato, ma sono raramente necessarie con Visual Basic .NET. Quando possibile, è consigliabile usare codice gestito dal .NET Framework per eseguire attività, anziché chiamate API Windows. In questa procedura dettagliata vengono fornite informazioni sulle situazioni in cui è necessario utilizzare le API di Windows.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Chiamate API con DECLARE  
 Il modo più comune per chiamare le API Windows consiste nell'utilizzare l' `Declare` istruzione.  
  
### <a name="to-declare-a-dll-procedure"></a>Per dichiarare una procedura DLL  
  
1. Determinare il nome della funzione che si desidera chiamare, più gli argomenti, i tipi di argomento e il valore restituito, nonché il nome e il percorso della DLL che lo contiene.  
  
    > [!NOTE]
    > Per informazioni complete sulle API Windows, vedere la documentazione di Win32 SDK nell'API Windows di Platform SDK. Per ulteriori informazioni sulle costanti utilizzate dalle API di Windows, esaminare i file di intestazione come Windows. h inclusi in Platform SDK.  
  
2. Aprire un nuovo progetto di applicazione Windows scegliendo **nuovo** dal menu **file** , quindi fare clic su **progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3. Selezionare **applicazione Windows** dall'elenco dei modelli di progetto Visual Basic. Verrà visualizzato il nuovo progetto.  
  
4. Aggiungere la `Declare` funzione seguente alla classe o al modulo in cui si vuole usare la dll:  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a>Parti dell'istruzione Declare  
 L' `Declare` istruzione include gli elementi seguenti.  
  
#### <a name="auto-modifier"></a>Modificatore automatico  
 Il `Auto` modificatore indica al runtime di convertire la stringa in base al nome del metodo in base alle regole Common Language Runtime (o al nome alias, se specificato).  
  
#### <a name="lib-and-alias-keywords"></a>Parole chiave lib e alias  
 Il nome che segue la `Function` parola chiave è il nome usato dal programma per accedere alla funzione importata. Può corrispondere al nome reale della funzione che si sta chiamando oppure è possibile utilizzare qualsiasi nome di routine valido e quindi utilizzare la `Alias` parola chiave per specificare il nome reale della funzione che si sta chiamando.  
  
 Specificare la `Lib` parola chiave, seguita dal nome e dal percorso della dll che contiene la funzione che si sta chiamando. Non è necessario specificare il percorso per i file presenti nelle directory di sistema di Windows.  
  
 Usare la `Alias` parola chiave se il nome della funzione che si sta chiamando non è un nome di stored procedure Visual Basic valido o è in conflitto con il nome di altri elementi nell'applicazione. `Alias`indica il nome true della funzione chiamata.  
  
#### <a name="argument-and-data-type-declarations"></a>Dichiarazioni di argomenti e tipi di dati  
 Dichiarare gli argomenti e i relativi tipi di dati. Questa parte può essere complessa perché i tipi di dati usati da Windows non corrispondono ai tipi di dati di Visual Studio. Visual Basic esegue una grande parte del lavoro convertendo gli argomenti in tipi di dati compatibili, un processo denominato *marshalling*. È possibile controllare in modo esplicito il modo in cui viene eseguito il marshalling degli argomenti utilizzando l' <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo definito nello <xref:System.Runtime.InteropServices> spazio dei nomi.  
  
> [!NOTE]
> Le versioni precedenti di Visual Basic consentivano di dichiarare parametri `As Any` , vale a dire che potevano essere utilizzati dati di qualsiasi tipo di dati. Visual Basic richiede l'utilizzo di un tipo di dati specifico per tutte le `Declare` istruzioni.  
  
#### <a name="windows-api-constants"></a>Costanti API Windows  
 Alcuni argomenti sono combinazioni di costanti. Ad esempio, l' `MessageBox` API mostrata in questa procedura dettagliata accetta un argomento integer denominato `Typ` che controlla la modalità di visualizzazione della finestra di messaggio. È possibile determinare il valore numerico di queste costanti esaminando le `#define` istruzioni nel file WinUser. h. I valori numerici sono in genere visualizzati in formato esadecimale, quindi è consigliabile usare un calcolatore per aggiungerli e convertirli in decimali. Se, ad esempio, si desidera combinare le costanti per il punto esclamativo `MB_ICONEXCLAMATION` 0x00000030 e il 0x00000004 di stile Yes/No `MB_YESNO` , è possibile aggiungere i numeri e ottenere un risultato di 0x00000034 o 52 Decimal. Sebbene sia possibile usare direttamente il risultato Decimal, è preferibile dichiarare questi valori come costanti nell'applicazione e combinarli usando l' `Or` operatore.  
  
##### <a name="to-declare-constants-for-windows-api-calls"></a>Per dichiarare costanti per le chiamate API Windows  
  
1. Consultare la documentazione per la funzione di Windows che si sta chiamando. Determinare il nome delle costanti utilizzate e il nome del file con estensione h che contiene i valori numerici per queste costanti.  
  
2. Utilizzare un editor di testo, ad esempio Blocco note, per visualizzare il contenuto del file di intestazione (. h) e individuare i valori associati alle costanti utilizzate. Ad esempio, l' `MessageBox` API usa la costante `MB_ICONQUESTION` per visualizzare un punto interrogativo nella finestra di messaggio. La definizione di `MB_ICONQUESTION` si trova in winuser. h e viene visualizzata come segue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. Aggiungere istruzioni equivalenti `Const` alla classe o al modulo per rendere queste costanti disponibili per l'applicazione. Ad esempio:  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a>Per chiamare la procedura DLL  
  
1. Aggiungere un pulsante denominato `Button1` al modulo di avvio per il progetto, quindi fare doppio clic su di esso per visualizzarne il codice. Viene visualizzato il gestore eventi per il pulsante.  
  
2. Aggiungere il codice al `Click` gestore eventi per il pulsante aggiunto, per chiamare la procedura e fornire gli argomenti appropriati:  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. Eseguire il progetto premendo F5. La finestra di messaggio viene visualizzata con i pulsanti **Sì** e **Nessuna** risposta. Fare clic su una delle due.  
  
#### <a name="data-marshaling"></a>Marshalling dei dati  
 Visual Basic converte automaticamente i tipi di dati dei parametri e i valori restituiti per le chiamate API Windows, ma è possibile usare l' `MarshalAs` attributo per specificare in modo esplicito i tipi di dati non gestiti previsti da un'API. Per ulteriori informazioni sul marshalling di interoperabilità, vedere [marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md).  
  
##### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Per usare DECLARE e marshalling in una chiamata API  
  
1. Determinare il nome della funzione che si desidera chiamare, più gli argomenti, i tipi di dati e il valore restituito.  
  
2. Per semplificare l'accesso all' `MarshalAs` attributo, aggiungere un' `Imports` istruzione all'inizio del codice per la classe o il modulo, come nell'esempio seguente:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. Aggiungere un prototipo di funzione per la funzione importata alla classe o al modulo in uso e applicare l' `MarshalAs` attributo ai parametri o al valore restituito. Nell'esempio seguente viene effettuato il marshalling di una chiamata API che prevede il tipo `void*` `AsAny` :  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a>Chiamate API con DllImport  
 L' `DllImport` attributo fornisce un secondo modo per chiamare le funzioni nelle DLL senza librerie dei tipi. `DllImport`è approssimativamente equivalente all'uso di un' `Declare` istruzione, ma offre un maggiore controllo sulla modalità di chiamata delle funzioni.  
  
 È possibile utilizzare `DllImport` con la maggior parte delle chiamate API Windows purché la chiamata faccia riferimento a un metodo condiviso (talvolta chiamato *statico*). Non è possibile usare metodi che richiedono un'istanza di una classe. Diversamente dalle `Declare` istruzioni, `DllImport` le chiamate non possono utilizzare l' `MarshalAs` attributo.  
  
### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Per chiamare un'API Windows utilizzando l'attributo DllImport  
  
1. Aprire un nuovo progetto di applicazione Windows scegliendo **nuovo** dal menu **file** , quindi fare clic su **progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2. Selezionare **applicazione Windows** dall'elenco dei modelli di progetto Visual Basic. Verrà visualizzato il nuovo progetto.  
  
3. Aggiungere un pulsante denominato `Button2` al modulo di avvio.  
  
4. Fare doppio clic `Button2` per aprire la visualizzazione codice per il form.  
  
5. Per semplificare l'accesso a `DllImport` , aggiungere un' `Imports` istruzione all'inizio del codice per la classe del form di avvio:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. Dichiarare una funzione vuota che precede l' `End Class` istruzione per il form e assegnare un nome alla funzione `MoveFile` .  
  
7. Applicare i `Public` `Shared` modificatori e alla dichiarazione di funzione e impostare i parametri per `MoveFile` in base agli argomenti utilizzati dalla funzione API di Windows:  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     La funzione può avere qualsiasi nome di routine valido; l' `DllImport` attributo specifica il nome nella dll. Gestisce anche il marshalling di interoperabilità per i parametri e i valori restituiti, quindi è possibile scegliere i tipi di dati di Visual Studio simili ai tipi di dati usati dall'API.  
  
8. Applicare l' `DllImport` attributo alla funzione vuota. Il primo parametro è il nome e il percorso della DLL che contiene la funzione che si sta chiamando. Non è necessario specificare il percorso per i file presenti nelle directory di sistema di Windows. Il secondo parametro è un argomento denominato che specifica il nome della funzione nell'API Windows. In questo esempio, l' `DllImport` attributo impone che le chiamate a `MoveFile` vengano trasmesse a `MoveFileW` in Kernel32. DLL. Il `MoveFileW` metodo copia un file dal percorso `src` al percorso `dst` .  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. Aggiungere il codice al `Button2_Click` gestore eventi per chiamare la funzione:  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. Creare un file denominato test. txt e inserirlo nella directory C:\Tmp sul disco rigido. Se necessario, creare la directory tmp.  
  
11. Premere F5 per avviare l’applicazione. Viene visualizzato il form principale.  
  
12. Fare clic su **Button2**. Il messaggio "il file è stato spostato correttamente" viene visualizzato se il file può essere spostato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Declare Statement](../../language-reference/statements/declare-statement.md)
- [Auto](../../language-reference/modifiers/auto.md)
- [Alias](../../language-reference/statements/alias-clause.md)
- [Interoperabilità COM](index.md)
- [Creazione di prototipi nel codice gestito](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Marshalling di un delegato come metodo di callback](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
