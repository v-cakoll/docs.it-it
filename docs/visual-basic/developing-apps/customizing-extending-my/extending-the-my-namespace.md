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
ms.openlocfilehash: 6da0914c9d2d4dc1220ede5d6fa9f1aa6b43426a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775292"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Estensione dello spazio dei nomi `My` in Visual Basic

Lo spazio dei nomi `My` in Visual Basic espone proprietà e metodi che consentono di sfruttare facilmente le potenzialità della .NET Framework. Lo spazio dei nomi `My` semplifica i problemi comuni di programmazione, riducendo spesso un'attività complessa a una singola riga di codice. Lo spazio dei nomi `My` è inoltre completamente estendibile, in modo che sia possibile personalizzare il comportamento di `My` e aggiungere nuovi servizi alla gerarchia per adattarsi alle specifiche esigenze dell'applicazione. In questo argomento viene illustrato come personalizzare i membri esistenti dello spazio dei nomi `My` e come aggiungere classi personalizzate allo spazio dei nomi `My`.

## <a name="customizing-existing-my-namespace-members"></a>Personalizzazione di membri dello spazio dei nomi `My` esistenti

Lo spazio dei nomi `My` in Visual Basic espone informazioni di uso frequente sull'applicazione, sul computer e altro ancora. Per un elenco completo degli oggetti nello spazio dei nomi `My`, vedere [My Reference](../../language-reference/keywords/my-reference.md). Potrebbe essere necessario personalizzare i membri esistenti dello spazio dei nomi `My` in modo che corrispondano meglio alle esigenze dell'applicazione. Qualsiasi proprietà di un oggetto nello spazio dei nomi `My` che non è di sola lettura può essere impostata su un valore personalizzato.

Si supponga, ad esempio, di utilizzare spesso l'oggetto `My.User` per accedere al contesto di sicurezza corrente per l'utente che esegue l'applicazione. Tuttavia, l'azienda usa un oggetto utente personalizzato per esporre informazioni e funzionalità aggiuntive per gli utenti all'interno dell'azienda. In questo scenario, è possibile sostituire il valore predefinito della proprietà `My.User.CurrentPrincipal` con un'istanza dell'oggetto Principal personalizzato, come illustrato nell'esempio seguente:

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

L'impostazione della proprietà `CurrentPrincipal` nell'oggetto `My.User` modifica l'identità con cui viene eseguita l'applicazione. L'oggetto `My.User`, a sua volta, restituisce informazioni sul nuovo utente specificato.
  
## <a name="adding-members-to-my-objects"></a>Aggiunta di membri a oggetti `My`

I tipi restituiti da `My.Application` e `My.Computer` sono definiti come classi `Partial`. È pertanto possibile estendere gli oggetti `My.Application` e `My.Computer` creando una classe `Partial` denominata `MyApplication` o `MyComputer`. La classe non può essere una classe `Private`. Se si specifica la classe come parte dello spazio dei nomi `My`, è possibile aggiungere proprietà e metodi che verranno inclusi con gli oggetti `My.Application` o `My.Computer`.

Nell'esempio seguente viene aggiunta una proprietà denominata `DnsServerIPAddresses` all'oggetto `My.Computer`:

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>Aggiunta di oggetti personalizzati allo spazio dei nomi `My`

Sebbene lo spazio dei nomi `My` fornisca soluzioni per molte attività di programmazione comuni, è possibile che si verifichino attività non indirizzate dallo spazio dei nomi `My`. Ad esempio, l'applicazione potrebbe accedere ai servizi directory personalizzati per i dati utente o l'applicazione potrebbe usare assembly che non sono installati per impostazione predefinita con Visual Basic. È possibile estendere lo spazio dei nomi `My` per includere soluzioni personalizzate a attività comuni specifiche per l'ambiente in uso. Lo spazio dei nomi `My` può essere facilmente esteso per aggiungere nuovi membri per soddisfare le esigenze di applicazioni in continua crescita. Inoltre, è possibile distribuire le estensioni dello spazio dei nomi `My` ad altri sviluppatori come modello di Visual Basic.
  
### <a name="adding-members-to-the-my-namespace"></a>Aggiunta di membri allo spazio dei nomi `My`

Poiché `My` è uno spazio dei nomi come qualsiasi altro spazio dei nomi, è possibile aggiungervi proprietà di primo livello aggiungendo semplicemente un modulo e specificando una `Namespace` di `My`. Annotare il modulo con l'attributo `HideModuleName` come illustrato nell'esempio seguente. L'attributo `HideModuleName` garantisce che in IntelliSense non venga visualizzato il nome del modulo quando vengono visualizzati i membri dello spazio dei nomi `My`.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

Per aggiungere membri allo spazio dei nomi `My`, aggiungere le proprietà necessarie al modulo. Per ogni proprietà aggiunta allo spazio dei nomi `My`, aggiungere un campo privato di tipo `ThreadSafeObjectProvider(Of T)`, in cui il tipo è il tipo restituito dalla proprietà personalizzata. Questo campo viene utilizzato per creare istanze di oggetti thread-safe che devono essere restituite dalla proprietà chiamando il metodo `GetInstance`. Di conseguenza, ogni thread che accede alla proprietà estesa riceve la propria istanza del tipo restituito. Nell'esempio seguente viene aggiunta una proprietà denominata `SampleExtension` di tipo `SampleExtension` allo spazio dei nomi `My`:

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>Aggiunta di eventi a oggetti `My` personalizzati

È possibile utilizzare l'oggetto `My.Application` per esporre gli eventi per gli oggetti `My` personalizzati estendendo la classe parziale `MyApplication` nello spazio dei nomi `My`. Per i progetti basati su Windows, è possibile fare doppio clic sul nodo **progetto** in per il progetto in **Esplora soluzioni**. Nella finestra di **progettazione del progetto**Visual Basic fare clic sulla scheda **applicazione** , quindi fare clic sul pulsante **Visualizza eventi applicazione** . Verrà creato un nuovo file denominato *ApplicationEvents. vb* . Contiene il codice seguente per estendere la classe `MyApplication`:

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

È possibile aggiungere gestori eventi per gli oggetti di `My` personalizzati aggiungendo gestori eventi personalizzati alla classe `MyApplication`. Gli eventi personalizzati consentono di aggiungere codice che verrà eseguito quando un gestore eventi viene aggiunto, rimosso o viene generato l'evento. Si noti che il codice `AddHandler` per un evento personalizzato viene eseguito solo se il codice viene aggiunto da un utente per gestire l'evento. Si consideri, ad esempio, che l'oggetto `SampleExtension` della sezione precedente presenta un evento `Load` a cui si desidera aggiungere un gestore eventi personalizzato. Nell'esempio di codice seguente viene illustrato un gestore eventi personalizzato denominato `SampleExtensionLoad` che verrà richiamato quando si verifica l'evento `My.SampleExtension.Load`. Quando viene aggiunto il codice per gestire il nuovo evento `My.SampleExtensionLoad`, viene eseguita la `AddHandler` parte del codice evento personalizzato. Il metodo `MyApplication_SampleExtensionLoad` è incluso nell'esempio di codice per mostrare un esempio di un gestore eventi che gestisce l'evento di `My.SampleExtensionLoad`. Si noti che l'evento `SampleExtensionLoad` sarà disponibile quando si seleziona l'opzione **eventi applicazione** nell'elenco a discesa a sinistra sopra l'editor di codice quando si modifica il file *ApplicationEvents. vb* .

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>Linee guida per la progettazione

Quando si sviluppano estensioni nello spazio dei nomi `My`, utilizzare le linee guida seguenti per ridurre al minimo i costi di manutenzione dei componenti di estensione:

- **Includere solo la logica di estensione.** La logica inclusa nell'estensione dello spazio dei nomi `My` deve includere solo il codice necessario per esporre la funzionalità necessaria nello spazio dei nomi `My`. Poiché l'estensione risiederà nei progetti utente come codice sorgente, l'aggiornamento del componente di estensione comporta un costo di manutenzione elevato e deve essere evitato, se possibile.
- **Ridurre al minimo i presupposti del progetto.** Quando si creano estensioni dello spazio dei nomi `My`, non presupporre un set di riferimenti, importazioni a livello di progetto o impostazioni specifiche del compilatore, ad esempio `Option Strict` disattivato. Al contrario, ridurre al minimo le dipendenze e qualificare completamente tutti i riferimenti ai tipi usando la parola chiave `Global`. Inoltre, verificare che l'estensione venga compilata con `Option Strict` on per ridurre al minimo gli errori nell'estensione.
- **Isolare il codice di estensione.** Inserendo il codice in un singolo file, l'estensione viene facilmente distribuibile come modello di elemento di Visual Studio. Per ulteriori informazioni, vedere "creazione di pacchetti e distribuzione di estensioni" più avanti in questo argomento. L'inserimento di tutti i `My` codice di estensione dello spazio dei nomi in un singolo file o in una cartella separata di un progetto consente inoltre agli utenti di individuare l'estensione dello spazio dei nomi `My`.

## <a name="designing-class-libraries-for-my"></a>Progettazione di librerie di classi per `My`

Come nel caso della maggior parte dei modelli a oggetti, alcuni modelli di progettazione funzionano correttamente nello spazio dei nomi `My` e altri no. Quando si progetta un'estensione per lo spazio dei nomi `My`, prendere in considerazione i principi seguenti:

- **Metodi senza stato.** I metodi nello spazio dei nomi `My` dovrebbero fornire una soluzione completa a un'attività specifica. Verificare che i valori dei parametri passati al metodo forniscano tutti gli input necessari per completare l'attività specifica. Evitare di creare metodi basati sullo stato precedente, ad esempio connessioni aperte alle risorse.
- **Istanze globali.** L'unico stato mantenuto nello spazio dei nomi `My` è globale per il progetto. Ad esempio, `My.Application.Info` incapsula lo stato condiviso nell'intera applicazione.
- **Tipi di parametri semplici.** È sufficiente evitare i tipi di parametro complessi. Creare invece metodi che non accettano input di parametro o che accettano tipi di input semplici, ad esempio stringhe, tipi primitivi e così via.
- **Metodi Factory.** Alcuni tipi sono necessariamente difficili da creare un'istanza. Fornire metodi factory come estensioni allo spazio dei nomi `My` consente di individuare e utilizzare più facilmente i tipi che rientrano in questa categoria. Un esempio di un metodo factory che funziona bene è `My.Computer.FileSystem.OpenTextFileReader`. Sono disponibili diversi tipi di flusso nel .NET Framework. Specificando i file di testo in modo specifico, il `OpenTextFileReader` consente all'utente di comprendere il flusso da usare.

Queste linee guida non escludono i principi di progettazione generali per le librerie di classi. Sono invece raccomandazioni ottimizzate per gli sviluppatori che usano Visual Basic e lo spazio dei nomi `My`. Per i principi di progettazione generali per la creazione di librerie di classi, vedere [linee guida di progettazione di Framework](../../../standard/design-guidelines/index.md).

## <a name="packaging-and-deploying-extensions"></a>Creazione di pacchetti e distribuzione di estensioni

È possibile includere `My` estensioni dello spazio dei nomi in un modello di progetto di Visual Studio oppure è possibile creare un pacchetto delle estensioni e distribuirle come modello di elemento di Visual Studio. Quando si impacchettano le estensioni dello spazio dei nomi `My` come modello di elemento di Visual Studio, è possibile sfruttare le funzionalità aggiuntive fornite da Visual Basic. Queste funzionalità consentono di includere un'estensione quando un progetto fa riferimento a un assembly specifico oppure consentire agli utenti di aggiungere in modo esplicito l'estensione dello spazio dei nomi `My` tramite la pagina **estensioni My** della finestra di progettazione del progetto Visual Basic.

Per informazioni dettagliate su come distribuire `My` estensioni dello spazio dei nomi, vedere Creazione del [pacchetto e distribuzione delle estensioni My personalizzate](packaging-and-deploying-custom-my-extensions.md).

## <a name="see-also"></a>Vedere anche

- [Assemblaggio e distribuzione delle estensioni My personalizzate](packaging-and-deploying-custom-my-extensions.md)
- [Estensione del modello di applicazione Visual Basic](extending-the-visual-basic-application-model.md)
- [Personalizzazione degli oggetti disponibili in My](customizing-which-objects-are-available-in-my.md)
- [Pagina Estensioni My, Creazione progetti](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../language-reference/modifiers/partial.md)
