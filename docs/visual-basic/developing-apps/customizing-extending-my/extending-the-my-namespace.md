---
title: Estensione dello spazio dei nomi My in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 31593fa8b0cc2670b9d59b8cd61ae66efd219269
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659763"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Estensione dello spazio dei nomi My in Visual Basic
Il `My` dello spazio dei nomi in Visual Basic espone le proprietà e metodi che consentono di sfruttare facilmente la potenza di .NET Framework. Il `My` dello spazio dei nomi semplifica i problemi di programmazione comuni, riducendo spesso un'attività difficile da una singola riga di codice. Inoltre, il `My` dello spazio dei nomi è completamente estendibile, in modo che sia possibile personalizzare il comportamento di `My` e aggiunta di nuovi servizi alla gerarchia di adattarsi alle esigenze specifiche dell'applicazione. Questo argomento illustra sia come personalizzare i membri esistenti del `My` dello spazio dei nomi e su come aggiungere le classi personalizzate per il `My` dello spazio dei nomi.  
  
 **Contenuto dell'argomento**  
  
- [Personalizzazione esistenti membri personale Namespace](#customizing)  
  
- [Aggiunta di membri a oggetti My](#addingtoobjects)  
  
- [Aggiunta di oggetti personalizzati per il mio Namespace](#addingcustom)  
  
- [Aggiunta di membri per il mio Namespace](#addingtonamespace)  
  
- [Aggiunta di eventi a oggetti My personalizzati](#addingevents)  
  
- [Linee guida di progettazione](#design)  
  
- [Progettazione di librerie di classi per My](#designing)  
  
- [Assemblaggio e distribuzione delle estensioni](#packaging)  
  
## <a name="customizing"></a> Personalizzazione esistenti membri personale Namespace  
 Il `My` dello spazio dei nomi in Visual Basic espone frequente informazioni sull'applicazione, il computer e così via. Per un elenco completo degli oggetti nel `My` dello spazio dei nomi, vedere [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Potrebbe essere necessario personalizzare i membri esistenti del `My` dello spazio dei nomi in modo da corrispondere meglio le esigenze dell'applicazione. Qualsiasi proprietà di un oggetto nel `My` dello spazio dei nomi che non è di sola lettura può essere impostato su un valore personalizzato.  
  
 Ad esempio supponga usati di frequente il `My.User` oggetto per accedere al contesto di sicurezza corrente per l'utente che esegue l'applicazione. Tuttavia, la società Usa un oggetto utente personalizzati per esporre funzionalità per gli utenti all'interno della società e informazioni aggiuntive. In questo scenario, è possibile sostituire il valore predefinito di `My.User.CurrentPrincipal` proprietà con un'istanza del proprio oggetto entità personalizzata, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]  
  
 Impostando il `CurrentPrincipal` proprietà di `My.User` oggetto viene modificato l'identità con cui viene eseguito l'applicazione. Il `My.User` oggetto, a sua volta, restituisce informazioni sull'utente appena specificato.  
  
## <a name="addingtoobjects"></a> Aggiunta di membri a oggetti My  
 I tipi restituiti da `My.Application` e `My.Computer` sono definiti come `Partial` classi. Pertanto, è possibile estendere il `My.Application` e `My.Computer` oggetti mediante la creazione di un `Partial` classe denominata `MyApplication` o `MyComputer`. La classe non può essere un `Private` classe. Se si specifica la classe come parte del `My` dello spazio dei nomi, è possibile aggiungere proprietà e metodi che verranno inclusi con il `My.Application` o `My.Computer` oggetti.  
  
 Ad esempio, l'esempio seguente aggiunge una proprietà denominata `DnsServerIPAddresses` per il `My.Computer` oggetto.  
  
 [!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]  
  
## <a name="addingcustom"></a> Aggiunta di oggetti personalizzati per il mio Namespace  
 Anche se il `My` dello spazio dei nomi fornisce soluzioni per molte attività di programmazione comune, che possono verificarsi attività che la `My` dello spazio dei nomi non viene risolto. Ad esempio, l'applicazione potrebbe accedere a servizi di directory personalizzata per i dati utente o l'applicazione potrebbe utilizzare gli assembly che non sono installati per impostazione predefinita con Visual Basic. È possibile estendere il `My` dello spazio dei nomi per includere soluzioni personalizzate per le attività comuni che sono specifiche dell'ambiente. Il `My` dello spazio dei nomi può essere facilmente esteso per aggiungere nuovi membri in base alle esigenze dell'applicazione in continua crescita. Inoltre, è possibile distribuire il `My` estensioni spazio dei nomi per gli altri sviluppatori come un modello di Visual Basic.  
  
### <a name="addingtonamespace"></a> Aggiunta di membri per il mio Namespace  
 In quanto `My` è uno spazio dei nomi come qualsiasi altro spazio dei nomi, è possibile aggiungere proprietà di livello superiore a esso semplicemente aggiungendo un modulo e specificando una `Namespace` di `My`. Annotare il modulo con il `HideModuleName` attributo come illustrato nell'esempio seguente. Il `HideModuleName` attributo assicura che il nome del modulo non venga visualizzato in IntelliSense quando visualizza i membri del `My` dello spazio dei nomi.  
  
 [!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]  
  
 Per aggiungere membri al `My` dello spazio dei nomi, aggiungere le proprietà necessarie per il modulo. Per ogni proprietà aggiunte per il `My` dello spazio dei nomi, aggiungere un campo privato di tipo `ThreadSafeObjectProvider(Of T)`, in cui il tipo è il tipo restituito dalla proprietà personalizzata. Questo campo viene usato per creare istanze di oggetti thread-safe che deve essere restituito dalla proprietà chiamando i `GetInstance` (metodo). Di conseguenza, ogni thread che accede alla proprietà estesa riceve la propria istanza del tipo restituito. L'esempio seguente aggiunge una proprietà denominata `SampleExtension` che è di tipo `SampleExtension` per il `My` dello spazio dei nomi:  
  
 [!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]  
  
## <a name="addingevents"></a> Aggiunta di eventi a oggetti My personalizzati  
 È possibile usare la `My.Application` oggetto di esporre gli eventi per personalizzata `My` oggetti estendendo il `MyApplication` classe parziale nel `My` dello spazio dei nomi. Per i progetti basati su Windows, è possibile fare doppio clic il **My Project** per il progetto nel nodo **Esplora soluzioni**. In Visual Basic **creazione progetti**, fare clic sui `Application` scheda e quindi fare clic su di `View Application Events` pulsante. Verrà creato un nuovo file denominato ApplicationEvents. vb. Contiene il codice seguente per estendere il `MyApplication` classe.  
  
 [!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]  
  
 È possibile aggiungere gestori eventi per personalizzata `My` oggetti mediante l'aggiunta di gestori di eventi personalizzati per il `MyApplication` classe. Eventi personalizzati consentono di aggiungere il codice che verrà eseguito quando un gestore eventi viene aggiunto, rimosso, o viene generato l'evento. Si noti che il `AddHandler` per un evento personalizzato viene eseguito solo se il codice viene aggiunto da un utente di gestire l'evento di codice. Ad esempio, è consigliabile che il `SampleExtension` oggetto nella sezione precedente ha un `Load` evento che si desidera aggiungere un gestore di evento personalizzato per. Esempio di codice seguente viene illustrato un gestore di evento personalizzato denominato `SampleExtensionLoad` che verrà richiamato quando il `My.SampleExtension.Load` evento si verifica. Quando viene aggiunto codice per gestire il nuovo `My.SampleExtensionLoad` evento, il `AddHandler` viene eseguita parte del codice evento personalizzato. Il `MyApplication_SampleExtensionLoad` metodo è incluso nell'esempio di codice per visualizzare un esempio di un gestore eventi che gestisce il `My.SampleExtensionLoad` evento. Si noti che il `SampleExtensionLoad` eventi saranno disponibili quando si seleziona il **gli eventi dell'applicazione My** opzione nell'elenco a discesa a sinistra sopra l'Editor del codice quando si modifica il file ApplicationEvents. vb.  
  
 [!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]  
  
## <a name="design"></a> Linee guida di progettazione  
 Quando si sviluppano estensioni per il `My` dello spazio dei nomi, usare le linee guida seguenti per ridurre al minimo i costi di manutenzione dei componenti dell'estensione.  
  
- **Includere solo la logica dell'estensione.** La logica inclusa nella `My` estensione dello spazio dei nomi deve includere solo il codice necessario per esporre la funzionalità richiesta nel `My` dello spazio dei nomi. Poiché l'estensione risiederanno nei progetti di utente come codice sorgente, aggiornando il componente di estensione comporta un costo di manutenzione elevato e deve essere evitata, se possibile.  
  
- **Ridurre al minimo i presupposti di progetto.** Quando si creano le estensioni del `My` dello spazio dei nomi, non presupporre un set di riferimenti, imports a livello di progetto o le impostazioni del compilatore specifici (ad esempio, `Option Strict` off). Al contrario, ridurre al minimo le dipendenze e tutti i riferimenti di tipo completi utilizzando il `Global` (parola chiave). Inoltre, assicurarsi che l'estensione venga compilato con `Option Strict` accensione per ridurre al minimo gli errori nell'estensione.  
  
- **Isolare il codice di estensione.** Inserire il codice in un singolo file rende l'estensione consente una semplice distribuzione come un modello di elemento di Visual Studio. Per altre informazioni, vedere "Creazione di pacchetti e distribuzione delle estensioni" più avanti in questo argomento. Inserimento di tutti i `My` codice dell'estensione dello spazio dei nomi in un singolo file o una cartella distinta in un progetto consentirà inoltre gli utenti individuare il `My` estensione dello spazio dei nomi.  
  
## <a name="designing"></a> Progettazione di librerie di classi per My  
 Come avviene con la maggior parte dei modelli a oggetti, alcuni schemi progettuali funzionano in modo efficiente il `My` dello spazio dei nomi e gli altri non lo sono. Quando si progetta un'estensione per il `My` dello spazio dei nomi, prendere in considerazione i principi seguenti:  
  
- **Metodi senza stati.** Metodi di `My` dello spazio dei nomi deve fornire una soluzione completa per un'attività specifica. Verificare che i valori dei parametri passati al metodo forniscano tutti gli input necessari per completare l'attività particolare. Evitare di creare metodi che si basano sullo stato precedente, ad esempio le connessioni aperte per le risorse.  
  
- **Istanze globali.** L'unico stato che viene mantenuto nel `My` dello spazio dei nomi è globale per il progetto. Ad esempio, `My.Application.Info` incapsula lo stato condiviso in tutta l'applicazione.  
  
- **Tipi di parametri semplici.** Semplificare le operazioni, evitando i tipi di parametri complessi. In alternativa, creare i metodi che uno accetta alcun parametro di input o che accettano tipi di input semplici come stringhe, i tipi primitivi e così via.  
  
- **Metodi factory.** Alcuni tipi sono necessariamente difficile creare un'istanza. Fornisce metodi factory come estensioni per il `My` dello spazio dei nomi consente di individuare più facilmente e utilizzano i tipi che rientrano in questa categoria. Un esempio di un metodo factory che offre risultati ottimali è `My.Computer.FileSystem.OpenTextFileReader`. Esistono diversi tipi di flusso disponibile in .NET Framework. Specificando i file di testo, in particolare, il `OpenTextFileReader` consente all'utente di comprendere il flusso da utilizzare.  
  
 Queste linee guida non esclude i principi di progettazione generale per le librerie di classi. Piuttosto, sono le raccomandazioni sono ottimizzate per gli sviluppatori che usano Visual Basic e `My` dello spazio dei nomi. Per i principi di progettazione generale per la creazione di librerie di classi, vedere [linee guida di progettazione di Framework](../../../standard/design-guidelines/index.md).  
  
## <a name="packaging"></a> Assemblaggio e distribuzione delle estensioni  
 È possibile includere `My` estensioni spazio dei nomi in un modello di progetto di Visual Studio, oppure è possano creare un pacchetto di estensioni e distribuirli come un modello di elemento di Visual Studio. Quando crei il pacchetto di `My` estensioni spazio dei nomi come un modello di elemento di Visual Studio, è possibile sfruttare le funzionalità aggiuntive fornite da Visual Basic. Queste funzionalità consentono di includere un'estensione quando un progetto fa riferimento a un determinato assembly o consentire agli utenti di aggiungere in modo esplicito il `My` estensione dello spazio dei nomi usando il **estensioni My** pagina di Visual Basic Creazione di progetti.  
  
 Per informazioni dettagliate su come distribuire `My` estensioni dello spazio dei nomi, vedere [creazione di pacchetti e distribuzione delle estensioni My personalizzate](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Assemblaggio e distribuzione delle estensioni My personalizzate](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)
- [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Pagina Estensioni My, Creazione progetti](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
