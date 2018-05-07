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
ms.openlocfilehash: 22d9d0def302b870de6f3e5ca4c142758b21314c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Estensione dello spazio dei nomi My in Visual Basic
Il `My` spazio dei nomi in Visual Basic espone proprietà e metodi che consentono di sfruttare facilmente la potenza di .NET Framework. Il `My` dello spazio dei nomi semplifica problemi comuni di programmazione, spesso riducendo un'attività complessa in una singola riga di codice. Inoltre, il `My` dello spazio dei nomi è completamente estendibile in modo che sia possibile personalizzare il comportamento di `My` e aggiungere nuovi servizi nella gerarchia per adattarsi alle esigenze specifiche dell'applicazione. Questo argomento illustra sia come personalizzare i membri esistenti del `My` dello spazio dei nomi e su come aggiungere le classi personalizzate per il `My` dello spazio dei nomi.  
  
 **Contenuto dell'argomento**  
  
-   [Personalizzazione esistenti membri personale Namespace](#customizing)  
  
-   [Aggiunta di membri a oggetti My](#addingtoobjects)  
  
-   [Aggiunta di oggetti personalizzati per il mio Namespace](#addingcustom)  
  
-   [Aggiunta di membri per il mio Namespace](#addingtonamespace)  
  
-   [Aggiunta di eventi a oggetti My personalizzati](#addingevents)  
  
-   [Linee guida di progettazione](#design)  
  
-   [Progettazione di librerie di classi per My](#designing)  
  
-   [Creazione del package e distribuzione di estensioni](#packaging)  
  
##  <a name="customizing"></a> Personalizzazione esistenti membri personale Namespace  
 Il `My` dello spazio dei nomi in Visual Basic espone frequente informazioni sull'applicazione, il computer e così via. Per un elenco completo degli oggetti di `My` dello spazio dei nomi, vedere [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Potrebbe essere necessario personalizzare i membri esistenti del `My` dello spazio dei nomi in modo da corrispondere meglio le esigenze dell'applicazione. Qualsiasi proprietà di un oggetto di `My` dello spazio dei nomi che non è di sola lettura può essere impostata su un valore personalizzato.  
  
 Ad esempio, si supponga che si usa spesso il `My.User` oggetto per accedere al contesto di sicurezza corrente per l'utente che esegue l'applicazione. Tuttavia, la società utilizza un oggetto utente personalizzato di esporre informazioni aggiuntive e funzionalità per gli utenti all'interno della società. In questo scenario, è possibile sostituire il valore predefinito di `My.User.CurrentPrincipal` proprietà con un'istanza di un oggetto principale personalizzato, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 L'impostazione di `CurrentPrincipal` proprietà la `My.User` l'identità con cui viene eseguito l'applicazione le modifiche dell'oggetto. Il `My.User` , a sua volta, restituisce informazioni sul gruppo appena specificato.  
  
##  <a name="addingtoobjects"></a> Aggiunta di membri a oggetti My  
 I tipi restituiti da `My.Application` e `My.Computer` sono definite come `Partial` classi. Pertanto, è possibile estendere il `My.Application` e `My.Computer` oggetti mediante la creazione di un `Partial` classe denominata `MyApplication` o `MyComputer`. La classe non può essere un `Private` classe. Se si specifica la classe come parte di `My` dello spazio dei nomi, è possibile aggiungere proprietà e metodi che verranno inclusi con il `My.Application` o `My.Computer` oggetti.  
  
 Ad esempio, nell'esempio seguente viene aggiunta una proprietà denominata `DnsServerIPAddresses` per il `My.Computer` oggetto.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> Aggiunta di oggetti personalizzati per il mio Namespace  
 Sebbene il `My` dello spazio dei nomi fornisce soluzioni per molte attività di programmazione comuni, possono verificarsi attività che il `My` dello spazio dei nomi non viene risolto. Ad esempio, l'applicazione potrebbe accedere a servizi di directory personalizzata per i dati utente o l'applicazione potrebbe utilizzare gli assembly che non sono installati per impostazione predefinita con Visual Basic. È possibile estendere il `My` dello spazio dei nomi da includere soluzioni personalizzate per le attività comuni che sono specifiche dell'ambiente. Il `My` dello spazio dei nomi può essere facilmente esteso per aggiungere nuovi membri per soddisfare le crescenti esigenze dell'applicazione. Inoltre, è possibile distribuire il `My` estensioni spazio dei nomi agli altri sviluppatori come modello di Visual Basic.  
  
###  <a name="addingtonamespace"></a> Aggiunta di membri per il mio Namespace  
 Poiché `My` è uno spazio dei nomi come qualsiasi altro spazio dei nomi, è possibile aggiungere una proprietà di primo livello a esso semplicemente l'aggiunta di un modulo e specificando un `Namespace` di `My`. Annotare il modulo con il `HideModuleName` attributo come illustrato nell'esempio seguente. Il `HideModuleName` attributo assicura che il nome del modulo non verrà visualizzato in IntelliSense quando vengono visualizzati i membri del `My` dello spazio dei nomi.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Per aggiungere membri di `My` dello spazio dei nomi, aggiungere le proprietà necessarie per il modulo. Per ogni proprietà aggiunta per il `My` dello spazio dei nomi, aggiungere un campo privato di tipo `ThreadSafeObjectProvider(Of T)`, dove il tipo è il tipo restituito dalla proprietà personalizzata. Questo campo viene usato per creare istanze di oggetti thread-safe che devono essere restituite dalla proprietà chiamando il `GetInstance` metodo. Di conseguenza, ogni thread che accede alla proprietà estesa riceve la propria istanza del tipo restituito. Nell'esempio seguente viene aggiunta una proprietà denominata `SampleExtension` che è di tipo `SampleExtension` per il `My` dello spazio dei nomi:  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> Aggiunta di eventi a oggetti My personalizzati  
 È possibile utilizzare il `My.Application` oggetto per esporre gli eventi per personalizzato `My` oggetti estendendo il `MyApplication` classe parziale nel `My` dello spazio dei nomi. Per i progetti basati su Windows, è possibile fare doppio clic il **progetto** nodo per il progetto in **Esplora**. In Visual Basic **progettazione**, fare clic su di `Application` scheda e quindi fare clic il `View Application Events` pulsante. Verrà creato un nuovo file denominato ApplicationEvents. vb. Contiene il codice seguente per estendere la `MyApplication` classe.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 È possibile aggiungere i gestori eventi per personalizzato `My` oggetti mediante l'aggiunta di gestori di eventi personalizzati per la `MyApplication` classe. Eventi personalizzati consentono di aggiungere codice che verrà eseguito quando un gestore eventi viene aggiunto, rimosso, o viene generato l'evento. Si noti che il `AddHandler` di codice per un evento personalizzato viene eseguito solo se il codice viene aggiunto da un utente di gestire l'evento. Si consideri ad esempio che il `SampleExtension` oggetto della sezione precedente ha un `Load` evento che si desidera aggiungere un gestore dell'evento personalizzato per. Esempio di codice seguente viene illustrato un gestore dell'evento personalizzato denominato `SampleExtensionLoad` che sarà richiamato quando il `My.SampleExtension.Load` si verifica l'evento. Quando viene aggiunto codice per gestire il nuovo `My.SampleExtensionLoad` evento, il `AddHandler` viene eseguita parte del codice evento personalizzato. Il `MyApplication_SampleExtensionLoad` metodo è incluso nell'esempio di codice per visualizzare un esempio di un gestore eventi che gestisce il `My.SampleExtensionLoad` evento. Si noti che il `SampleExtensionLoad` eventi saranno disponibili quando si seleziona il **eventi applicazioni** opzione nell'elenco di riepilogo a discesa a sinistra, sopra l'Editor del codice quando si modifica il file ApplicationEvents. vb.  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> Linee guida di progettazione  
 Quando si sviluppano le estensioni per il `My` dello spazio dei nomi, utilizzare le linee guida seguenti per ridurre al minimo i costi di manutenzione dei componenti di estensione.  
  
-   **Include solo la logica di estensione.** La logica del `My` estensione spazio dei nomi deve includere solo il codice che è necessario esporre la funzionalità richiesta nel `My` dello spazio dei nomi. Perché l'estensione risiederanno nei progetti di utente come codice sorgente, l'aggiornamento del componente di estensione comporta un costo di manutenzione elevata e deve essere evitato se possibile.  
  
-   **Ridurre al minimo ipotesi di progetto.** Quando si creano le estensioni del `My` dello spazio dei nomi, non presupporre che un set di riferimenti, le importazioni a livello di progetto o le impostazioni del compilatore specifici (ad esempio, `Option Strict` off). Al contrario, ridurre al minimo le dipendenze e completare tutti i riferimenti di tipo utilizzando il `Global` (parola chiave). Inoltre, assicurarsi che l'estensione venga compilata con `Option Strict` per ridurre al minimo gli errori nell'estensione.  
  
-   **Isolare il codice di estensione.** Inserire il codice in un singolo file l'estensione rende facile distribuzione come un modello di elemento di Visual Studio. Per ulteriori informazioni, vedere "Creazione di pacchetti e distribuzione di estensioni" più avanti in questo argomento. Inserimento di tutti i `My` codice dell'estensione dello spazio dei nomi in un singolo file o una cartella distinta in un progetto verrà inoltre consentire agli utenti di individuare il `My` estensione spazio dei nomi.  
  
##  <a name="designing"></a> Progettazione di librerie di classi per My  
 Come accade con la maggior parte dei modelli a oggetti, alcuni modelli di progettazione funzionano in modo efficiente il `My` dello spazio dei nomi e gli altri non. Quando si progetta un'estensione per il `My` dello spazio dei nomi, considerare i principi seguenti:  
  
-   **Metodi senza stati.** Metodi di `My` dello spazio dei nomi deve fornire una soluzione completa per un'attività specifica. Verificare che i valori dei parametri passati al metodo forniscano tutti gli input necessario per completare l'attività particolare. Evitare di creare metodi che si basano sullo stato precedente, ad esempio le connessioni aperte alle risorse.  
  
-   **Istanze globali.** L'unico stato che viene mantenuto il `My` spazio dei nomi è globale per il progetto. Ad esempio, `My.Application.Info` incapsula lo stato condiviso in tutta l'applicazione.  
  
-   **Tipi di parametro semplici.** Semplicità, evitando di tipi di parametri complessi. In alternativa, creare metodi che non accettare nessun parametro di input o che accettano tipi di input semplici come stringhe, i tipi primitivi e così via.  
  
-   **Metodi factory.** Alcuni tipi sono necessariamente difficile creare un'istanza. Fornisce metodi factory come estensioni per il `My` dello spazio dei nomi consente di individuare più facilmente e utilizzare tipi che rientrano in questa categoria. Un esempio di un metodo factory che funziona bene è `My.Computer.FileSystem.OpenTextFileReader`. Sono disponibili diversi tipi di flusso in .NET Framework. Specificando i file di testo, in particolare, il `OpenTextFileReader` consente all'utente di capire quale flusso da utilizzare.  
  
 Queste linee guida non esclude i principi di progettazione generali per le librerie di classi. Piuttosto, sono raccomandazioni ottimizzate per gli sviluppatori che utilizzano Visual Basic e `My` dello spazio dei nomi. Per i principi di progettazione generali per la creazione di librerie di classi, vedere [linee guida](../../../standard/design-guidelines/index.md).  
  
##  <a name="packaging"></a> Creazione del package e distribuzione di estensioni  
 È possibile includere `My` estensioni spazio dei nomi in un modello di progetto di Visual Studio oppure è possono comprimere le estensioni e distribuirli come un modello di elemento di Visual Studio. Quando crei il pacchetto del `My` estensioni spazio dei nomi come un modello di elemento di Visual Studio, è possibile sfruttare le funzionalità aggiuntive fornite da Visual Basic. Queste funzionalità consentono di includere un'estensione quando un progetto fa riferimento a un particolare assembly o consentire agli utenti di aggiungere in modo esplicito il `My` estensione spazio dei nomi tramite il **estensioni My** pagina di Visual Basic Progettazione progetti.  
  
 Per informazioni dettagliate su come distribuire `My` estensioni spazio dei nomi, vedere [sui pacchetti e distribuzione delle estensioni My personalizzate](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Assemblaggio e distribuzione delle estensioni My personalizzate](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Pagina Estensioni My, Progettazione progetti](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)  
 [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
