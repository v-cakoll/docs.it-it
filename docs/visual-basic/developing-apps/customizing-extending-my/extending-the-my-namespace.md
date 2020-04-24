---
title: Estensione dello spazio dei nomi My
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 2a7b0b84061fccd9a333a68e4a19477bd19ca4ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330305"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Estensione dello `My` spazio dei nomi in Visual Basic

Lo `My` spazio dei nomi in Visual Basic espone proprietà e metodi che consentono di sfruttare facilmente la potenza del .NET Framework. Lo `My` spazio dei nomi semplifica i problemi di programmazione comuni, riducendo spesso un'attività complessa a una singola riga di codice. Lo `My` spazio dei nomi è inoltre completamente estendibile, in modo che sia possibile `My` personalizzare il comportamento di e aggiungere nuovi servizi alla gerarchia per adattarsi alle specifiche esigenze dell'applicazione. In questo argomento viene illustrato come personalizzare i membri esistenti dello `My` spazio dei nomi e come aggiungere classi personalizzate allo `My` spazio dei nomi.

## <a name="customizing-existing-my-namespace-members"></a>Personalizzazione di membri `My` dello spazio dei nomi esistenti

Lo `My` spazio dei nomi in Visual Basic espone le informazioni usate di frequente sull'applicazione, sul computer e altro ancora. Per un elenco completo degli oggetti nello `My` spazio dei nomi, vedere [My Reference](../../language-reference/keywords/my-reference.md). Potrebbe essere necessario personalizzare i membri esistenti dello `My` spazio dei nomi in modo che corrispondano meglio alle esigenze dell'applicazione. Qualsiasi proprietà di un oggetto nello `My` spazio dei nomi che non è di sola lettura può essere impostata su un valore personalizzato.

Si supponga, ad esempio, di utilizzare spesso `My.User` l'oggetto per accedere al contesto di sicurezza corrente per l'utente che esegue l'applicazione. Tuttavia, l'azienda usa un oggetto utente personalizzato per esporre informazioni e funzionalità aggiuntive per gli utenti all'interno dell'azienda. In questo scenario, è possibile sostituire il valore predefinito della `My.User.CurrentPrincipal` proprietà con un'istanza dell'oggetto Principal personalizzato, come illustrato nell'esempio seguente:

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

L'impostazione `CurrentPrincipal` della proprietà nell' `My.User` oggetto modifica l'identità con cui viene eseguita l'applicazione. L' `My.User` oggetto, a sua volta, restituisce le informazioni relative all'utente appena specificato.
  
## <a name="adding-members-to-my-objects"></a>Aggiunta di membri `My` a oggetti

I tipi restituiti da `My.Application` e `My.Computer` sono definiti come `Partial` classi. Pertanto, è possibile estendere gli `My.Application` oggetti `My.Computer` e creando una `Partial` classe denominata `MyApplication` o. `MyComputer` La classe non può essere `Private` una classe. Se si specifica la classe come parte dello `My` spazio dei nomi, è possibile aggiungere proprietà e metodi che verranno inclusi con gli `My.Application` oggetti `My.Computer` o.

Nell'esempio seguente viene aggiunta una proprietà `DnsServerIPAddresses` denominata all' `My.Computer` oggetto:

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>Aggiunta di oggetti personalizzati allo `My` spazio dei nomi

Sebbene lo `My` spazio dei nomi fornisca soluzioni per molte attività di programmazione comuni, è possibile che `My` si verifichino attività non indirizzate dallo spazio dei nomi. Ad esempio, l'applicazione potrebbe accedere ai servizi directory personalizzati per i dati utente o l'applicazione potrebbe usare assembly che non sono installati per impostazione predefinita con Visual Basic. È possibile estendere lo `My` spazio dei nomi per includere soluzioni personalizzate a attività comuni specifiche per l'ambiente in uso. Lo `My` spazio dei nomi può essere facilmente esteso per aggiungere nuovi membri per soddisfare le esigenze di applicazioni in continua crescita. Inoltre, è possibile distribuire le `My` estensioni dello spazio dei nomi ad altri sviluppatori come modello di Visual Basic.
  
### <a name="adding-members-to-the-my-namespace"></a>Aggiunta di membri allo `My` spazio dei nomi

Poiché `My` è uno spazio dei nomi come qualsiasi altro spazio dei nomi, è possibile aggiungervi proprietà di primo livello aggiungendo semplicemente un modulo e `Namespace` specificando un di `My`. Aggiungere annotazioni al modulo `HideModuleName` con l'attributo, come illustrato nell'esempio seguente. L' `HideModuleName` attributo garantisce che in IntelliSense non venga visualizzato il nome del modulo quando vengono visualizzati i membri `My` dello spazio dei nomi.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

Per aggiungere membri allo `My` spazio dei nomi, aggiungere le proprietà necessarie al modulo. Per ogni proprietà aggiunta allo `My` spazio dei nomi, aggiungere un campo privato di `ThreadSafeObjectProvider(Of T)`tipo, in cui il tipo è il tipo restituito dalla proprietà personalizzata. Questo campo viene utilizzato per creare istanze di oggetti thread-safe che devono essere restituite dalla proprietà chiamando `GetInstance` il metodo. Di conseguenza, ogni thread che accede alla proprietà estesa riceve la propria istanza del tipo restituito. Nell'esempio seguente viene aggiunta una proprietà `SampleExtension` denominata di tipo `SampleExtension` allo `My` spazio dei nomi:

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>Aggiunta di eventi a `My` oggetti personalizzati

È possibile utilizzare l' `My.Application` oggetto per esporre gli eventi per gli `My` oggetti personalizzati estendendo la `MyApplication` classe parziale `My` nello spazio dei nomi. Per i progetti basati su Windows, è possibile fare doppio clic sul nodo **progetto** in per il progetto in **Esplora soluzioni**. Nella finestra di **progettazione del progetto**Visual Basic fare clic sulla scheda **applicazione** , quindi fare clic sul pulsante **Visualizza eventi applicazione** . Verrà creato un nuovo file denominato *ApplicationEvents. vb* . Contiene il codice seguente per estendere la `MyApplication` classe:

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

È possibile aggiungere gestori eventi per gli oggetti personalizzati `My` aggiungendo gestori eventi personalizzati alla `MyApplication` classe. Gli eventi personalizzati consentono di aggiungere codice che verrà eseguito quando un gestore eventi viene aggiunto, rimosso o viene generato l'evento. Si noti che `AddHandler` il codice per un evento personalizzato viene eseguito solo se il codice viene aggiunto da un utente per gestire l'evento. Si consideri, ad `SampleExtension` esempio, che l'oggetto della sezione `Load` precedente presenta un evento per il quale si desidera aggiungere un gestore eventi personalizzato. Nell'esempio di codice seguente viene illustrato un gestore eventi `SampleExtensionLoad` personalizzato denominato che verrà richiamato `My.SampleExtension.Load` quando si verifica l'evento. Quando si aggiunge codice per gestire il nuovo `My.SampleExtensionLoad` evento, viene `AddHandler` eseguita la parte del codice evento personalizzato. Il `MyApplication_SampleExtensionLoad` metodo è incluso nell'esempio di codice per mostrare un esempio di un gestore eventi che gestisce l' `My.SampleExtensionLoad` evento. Si noti che `SampleExtensionLoad` l'evento sarà disponibile quando si seleziona l'opzione **eventi applicazione personali** nell'elenco a discesa a sinistra sopra l'editor di codice quando si modifica il file *ApplicationEvents. vb* .

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>Linee guida per la progettazione

Quando si sviluppano estensioni allo `My` spazio dei nomi, usare le linee guida seguenti per ridurre al minimo i costi di manutenzione dei componenti di estensione:

- **Includere solo la logica di estensione.** La logica inclusa nell'estensione `My` dello spazio dei nomi deve includere solo il codice necessario per esporre la funzionalità necessaria nello `My` spazio dei nomi. Poiché l'estensione risiederà nei progetti utente come codice sorgente, l'aggiornamento del componente di estensione comporta un costo di manutenzione elevato e deve essere evitato, se possibile.
- **Ridurre al minimo i presupposti del progetto.** Quando si creano le estensioni dello `My` spazio dei nomi, non presupporre un set di riferimenti, importazioni a livello di progetto o impostazioni del compilatore specifiche `Option Strict` (ad esempio, off). Al contrario, ridurre al minimo le dipendenze e qualificare completamente tutti `Global` i riferimenti ai tipi usando la parola chiave. Inoltre, verificare che l'estensione venga compilata con `Option Strict` on per ridurre al minimo gli errori nell'estensione.
- **Isolare il codice di estensione.** Inserendo il codice in un singolo file, l'estensione viene facilmente distribuibile come modello di elemento di Visual Studio. Per ulteriori informazioni, vedere "creazione di pacchetti e distribuzione di estensioni" più avanti in questo argomento. L'inserimento di `My` tutto il codice di estensione dello spazio dei nomi in un singolo file o in una cartella separata in un `My` progetto consente inoltre agli utenti di individuare l'estensione dello spazio dei nomi.

## <a name="designing-class-libraries-for-my"></a>Progettazione di librerie di classi per`My`

Come nel caso della maggior parte dei modelli a oggetti, alcuni modelli di progettazione funzionano `My` correttamente nello spazio dei nomi e altri no. Quando si progetta un'estensione dello `My` spazio dei nomi, prendere in considerazione i principi seguenti:

- **Metodi senza stato.** I `My` metodi nello spazio dei nomi devono fornire una soluzione completa a un'attività specifica. Verificare che i valori dei parametri passati al metodo forniscano tutti gli input necessari per completare l'attività specifica. Evitare di creare metodi basati sullo stato precedente, ad esempio connessioni aperte alle risorse.
- **Istanze globali.** L'unico stato mantenuto nello `My` spazio dei nomi è globale per il progetto. Ad esempio, `My.Application.Info` incapsula lo stato condiviso nell'intera applicazione.
- **Tipi di parametri semplici.** È sufficiente evitare i tipi di parametro complessi. Creare invece metodi che non accettano input di parametro o che accettano tipi di input semplici, ad esempio stringhe, tipi primitivi e così via.
- **Metodi Factory.** Alcuni tipi sono necessariamente difficili da creare un'istanza. Fornire metodi factory come estensioni allo spazio `My` dei nomi consente di individuare e utilizzare più facilmente i tipi che rientrano in questa categoria. Un esempio di un metodo factory che funziona bene è `My.Computer.FileSystem.OpenTextFileReader`. Sono disponibili diversi tipi di flusso nel .NET Framework. Specificando i file di testo in `OpenTextFileReader` modo specifico, consente all'utente di comprendere il flusso da usare.

Queste linee guida non escludono i principi di progettazione generali per le librerie di classi. Sono invece raccomandazioni ottimizzate per gli sviluppatori che usano Visual Basic e lo `My` spazio dei nomi. Per i principi di progettazione generali per la creazione di librerie di classi, vedere [linee guida di progettazione di Framework](../../../standard/design-guidelines/index.md).

## <a name="packaging-and-deploying-extensions"></a>Creazione di pacchetti e distribuzione di estensioni

È possibile includere `My` le estensioni dello spazio dei nomi in un modello di progetto di Visual Studio oppure è possibile creare un pacchetto delle estensioni e distribuirle come modello di elemento di Visual Studio. Quando si impacchettano `My` le estensioni dello spazio dei nomi come modello di elemento di Visual Studio, è possibile sfruttare le funzionalità aggiuntive fornite da Visual Basic. Queste funzionalità consentono di includere un'estensione quando un progetto fa riferimento a un assembly specifico oppure consentire agli utenti di aggiungere in modo `My` esplicito l'estensione dello spazio dei nomi tramite la pagina **estensioni My** della finestra di progettazione del Visual Basic.

Per informazioni dettagliate su come distribuire `My` le estensioni dello spazio dei nomi, vedere Creazione del [pacchetto e distribuzione delle estensioni My personalizzate](packaging-and-deploying-custom-my-extensions.md).

## <a name="see-also"></a>Vedi anche

- [Assemblaggio e distribuzione delle estensioni My personalizzate](packaging-and-deploying-custom-my-extensions.md)
- [Estensione del modello di applicazione Visual Basic](extending-the-visual-basic-application-model.md)
- [Personalizzazione degli oggetti disponibili in My](customizing-which-objects-are-available-in-my.md)
- [Pagina Estensioni My, Creazione progetti](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Parziale](../../language-reference/modifiers/partial.md)
