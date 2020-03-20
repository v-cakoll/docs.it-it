---
title: Architettura Impostazioni applicazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 078b5f3fc1cd4273af282580f41e68ca9bd8ff51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182617"
---
# <a name="application-settings-architecture"></a>Architettura Impostazioni applicazione
Questo argomento descrive il funzionamento dell'architettura Impostazioni applicazione e ne analizza le funzionalità avanzate, come i raggruppamenti e le chiavi delle impostazioni.

 L'architettura di Impostazioni applicazione supporta la definizione delle impostazioni fortemente tipizzate con ambito di applicazione o utente e la persistenza delle impostazioni tra sessioni dell'applicazione. L'architettura fornisce un motore di persistenza predefinito per salvare le impostazioni e caricarle dal file system locale. L'architettura definisce inoltre le interfacce per offrire un motore di persistenza personalizzato.

 Si tratta di interfacce che consentono ai componenti personalizzati di mantenere le proprie impostazioni quando sono ospitati in un'applicazione. Usando le chiavi delle impostazioni, i componenti possono mantenere le impostazioni per più istanze del componente separato.

## <a name="defining-settings"></a>Definizione delle impostazioni
 L'architettura delle impostazioni dell'applicazione viene utilizzata sia all'interno di ASP.NET e Windows Form e contiene una serie di classi di base condivise in entrambi gli ambienti. Il più <xref:System.Configuration.SettingsBase>importante è , che fornisce l'accesso alle impostazioni tramite una raccolta e fornisce metodi di basso livello per il caricamento e il salvataggio delle impostazioni. Ogni ambiente implementa la <xref:System.Configuration.SettingsBase> propria classe derivata da per fornire funzionalità di impostazioni aggiuntive per tale ambiente. In un'applicazione basata su Windows Form, tutte le <xref:System.Configuration.ApplicationSettingsBase> impostazioni dell'applicazione devono essere definite in una classe derivata dalla classe , che aggiunge la seguente funzionalità alla classe base:

- Caricamento e salvataggio delle operazioni di livello superiore

- Supporto per le impostazioni con ambito utente

- Ripristino delle impostazioni dell'utente alle impostazioni predefinite

- Aggiornamento delle impostazioni da una versione precedente dell'applicazione

- Convalida delle impostazioni, prima che vengano modificate o prima che vengano salvate

 Le impostazioni possono essere descritte utilizzando <xref:System.Configuration> una serie di attributi definiti all'interno dello spazio dei nomi; questi sono descritti in [Attributi delle impostazioni dell'applicazione](application-settings-attributes.md). Quando si definisce un'impostazione, <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute>è necessario applicarla con o , che descrive se l'impostazione si applica all'intera applicazione o solo all'utente corrente.

 L'esempio di codice seguente definisce una classe di impostazioni personalizzate con una singola impostazione, `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Persistenza delle impostazioni
 La <xref:System.Configuration.ApplicationSettingsBase> classe non mantiene o carica le impostazioni; questo processo ricade sul provider di impostazioni, una classe che deriva da <xref:System.Configuration.SettingsProvider>. Se una classe <xref:System.Configuration.ApplicationSettingsBase> derivata di non <xref:System.Configuration.SettingsProviderAttribute>specifica un provider <xref:System.Configuration.LocalFileSettingsProvider>di impostazioni tramite il , viene utilizzato il provider predefinito , , , .

 Il sistema di configurazione originariamente rilasciato con .NET Framework supporta la fornitura di dati statici `app.`di configurazione dell'applicazione tramite il file machine.config del computer locale o all'interno di un file exe.config distribuito con l'applicazione. La <xref:System.Configuration.LocalFileSettingsProvider> classe espande questo supporto nativo nei modi seguenti:The class expands this native support in the following ways:

- Le impostazioni con ambito applicazione possono essere archiviate in entrambi i file machine.config o `app.`exe.config. Il file machine.config è sempre di sola lettura, mentre `app`.exe.config è limitato dalle considerazioni sulla sicurezza alla sola lettura per la maggior parte delle applicazioni.

- Le impostazioni con ambito di utente possono essere archiviate in `app`.exe.config, in questo caso vengono considerate come valori predefiniti statici.

- Le impostazioni con ambito di utente non predefinite sono archiviate in un nuovo file *utente*.config, dove *user* è il nome dell'utente che esegue l'applicazione in quel momento. È possibile specificare un valore predefinito <xref:System.Configuration.DefaultSettingValueAttribute>per un'impostazione con ambito di utente con . Poiché le impostazioni con ambito utente spesso cambiano durante l'esecuzione dell'applicazione, `user`.config è sempre di lettura o scrittura.

 I tre file di configurazione archiviano le impostazioni in formato XML. L'elemento XML di livello superiore per le impostazioni con ambito di applicazione è `<appSettings>`, mentre `<userSettings>` viene usato per le impostazioni con ambito di utente. Un file `app`.exe.config che contiene sia le impostazioni con ambito di applicazione che quelle predefinite per le impostazioni con ambito utente si presenta come segue:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
        </sectionGroup>
    </configSections>
    <applicationSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="Cursor" serializeAs="String">
                <value>Default</value>
            </setting>
            <setting name="DoubleBuffering" serializeAs="String">
                <value>False</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </applicationSettings>
    <userSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="FormTitle" serializeAs="String">
                <value>Form1</value>
            </setting>
            <setting name="FormSize" serializeAs="String">
                <value>595, 536</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </userSettings>
</configuration>
```

 Per una definizione degli elementi all'interno della sezione di impostazioni applicazione di un file di configurazione, vedere [Application Settings Schema](../../configure-apps/file-schema/application-settings-schema.md) (Schema di impostazioni applicazione).

### <a name="settings-bindings"></a>Associazioni delle impostazioni
 Le impostazioni applicazione usano l'architettura di associazione dati di Windows Form per consentire la comunicazione bidirezionale degli aggiornamenti delle impostazioni tra i componenti e l'oggetto impostazioni. Se si usa Visual Studio per creare le impostazioni dell'applicazione e assegnarle alle proprietà del componente, queste associazioni vengono generate automaticamente.

 È possibile associare un'impostazione dell'applicazione solo a un componente che supporta l'interfaccia. <xref:System.Windows.Forms.IBindableComponent> Inoltre, il componente deve implementare un evento di modifica per una proprietà <xref:System.ComponentModel.INotifyPropertyChanged> associata specifica o notificare alle impostazioni dell'applicazione che la proprietà è stata modificata tramite l'interfaccia. Se il componente <xref:System.Windows.Forms.IBindableComponent> non implementa e si esegue l'associazione tramite Visual Studio, le proprietà associate verranno impostate la prima volta, ma non verranno aggiornate. Se il <xref:System.Windows.Forms.IBindableComponent> componente implementa ma non supporta le notifiche di modifica delle proprietà, l'associazione non verrà aggiornata nel file di impostazioni quando la proprietà viene modificata.

 Alcuni componenti di Windows <xref:System.Windows.Forms.ToolStripItem>Form, ad esempio , non supportano le associazioni delle impostazioni.

### <a name="settings-serialization"></a>Serializzazione delle impostazioni
 Quando <xref:System.Configuration.LocalFileSettingsProvider> è necessario salvare le impostazioni su disco, esegue le seguenti azioni:

1. Utilizza la reflection per esaminare <xref:System.Configuration.ApplicationSettingsBase> tutte le proprietà definite nella <xref:System.Configuration.ApplicationScopedSettingAttribute> classe <xref:System.Configuration.UserScopedSettingAttribute>derivata, individuando quelle applicate con o .

2. Serializza la proprietà su disco. Tenta innanzitutto di <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> chiamare il o <xref:System.ComponentModel.TypeConverter>sul tipo associato . Se il tentativo non riesce, usa la serializzazione XML.

3. Determina quali impostazioni vanno inserite in ciascun file, in base all'attributo dell'impostazione.

 Se si implementa una classe di <xref:System.Configuration.SettingsSerializeAsAttribute> impostazioni personalizzata, è possibile usare <xref:System.Configuration.SettingsSerializeAs> l'oggetto per contrassegnare un'impostazione per la serializzazione binaria o personalizzata utilizzando l'enumerazione . Per altre informazioni sulla creazione della propria classe di impostazioni nel codice, vedere [How to: Create Application Settings](how-to-create-application-settings.md) (Procedura: creare impostazioni applicazioni).

### <a name="settings-file-locations"></a>Percorsi del file delle installazioni
 Il percorso dei file `app`.exe.config e *user*.config variano in base alle modalità di installazione dell'applicazione. Per un'applicazione basata su Windows Form `app`copiata nel computer locale, exe.config risiederà nella stessa directory della directory di base del file <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> eseguibile principale dell'applicazione e *user*.config risiederà nel percorso specificato dalla proprietà . Per un'applicazione installata tramite ClickOnce, entrambi questi file risiederanno nella directory dei\\dati ClickOnce sotto %InstallRoot%, Documents and Settings*nomeutente*: Impostazioni locali.

 Il percorso di archiviazione di questi file è leggermente diverso se un utente ha abilitato i profili comuni, che consente a un utente di definire diverse impostazioni di Windows e dell'applicazione quando utilizzano altri computer all'interno di un dominio. In tal caso, sia le applicazioni ClickOnce che `app`le applicazioni non ClickOnce disfaranno dei file\\.exe.config e *user.config*archiviati in %InstallRoot%, Documents and Settings*nomeutente*: Dati applicazioni.

 Per altre informazioni sul funzionamento delle funzioni di Impostazioni applicazione con la nuova tecnologia di distribuzione, vedere [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings). Per ulteriori informazioni sulla directory dei dati ClickOnce, vedere [Accesso a dati locali e remoti nelle applicazioni ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).

## <a name="application-settings-and-security"></a>Impostazioni e sicurezza dell'applicazione
 Le impostazioni dell'applicazione sono progettate per funzionare in attendibilità parziale, un ambiente con restrizioni predefinito per le applicazioni di Windows Form ospitate in Internet o intranet. Non sono necessarie autorizzazioni speciali oltre all'attendibilità parziale per usare le impostazioni dell'applicazione con il provider di impostazioni predefinito.

 Quando le impostazioni dell'applicazione vengono `user`utilizzate in un'applicazione ClickOnce, il file con estensione config viene archiviato nella directory dei dati ClickOnce. La dimensione del file `user`config dell'applicazione non può superare la quota della directory dei dati impostata da ClickOnce. Per altre informazioni, vedere [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Provider di impostazioni personalizzate
 Nell'architettura Impostazioni applicazione è presente un accoppiamento libero tra la <xref:System.Configuration.ApplicationSettingsBase>classe wrapper delle impostazioni delle applicazioni, derivata da , e il provider o i provider di impostazioni associati, derivati da <xref:System.Configuration.SettingsProvider>. Questa associazione è <xref:System.Configuration.SettingsProviderAttribute> definita solo dall'oggetto applicato alla classe wrapper o alle singole proprietà. Se un provider di impostazioni non viene <xref:System.Configuration.LocalFileSettingsProvider>specificato in modo esplicito, viene utilizzato il provider predefinito, , . Di conseguenza, questa architettura supporta la creazione e l'uso di provider di impostazioni personalizzate.

 Si supponga, ad esempio, di voler sviluppare e usare `SqlSettingsProvider`, un provider che archivierà tutti i dati delle impostazioni in un database Microsoft SQL Server. La <xref:System.Configuration.SettingsProvider>classe derivata dalla classe `Initialize` riceverà queste <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>informazioni nel relativo metodo come parametro di tipo . È quindi necessario <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> implementare il metodo per recuperare <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> le impostazioni dall'archivio dati e salvarle. Il provider può <xref:System.Configuration.SettingsPropertyCollection> utilizzare <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> l'oggetto fornito per determinare il nome, il tipo e l'ambito della proprietà, nonché qualsiasi altro attributo di impostazioni definito per tale proprietà.

 Il provider dovrà implementare una proprietà e un metodo le cui implementazioni possono non essere evidenti. La <xref:System.Configuration.SettingsProvider.ApplicationName%2A> proprietà è una <xref:System.Configuration.SettingsProvider>proprietà astratta di ; è necessario programmarlo per restituire quanto segue:

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 La classe derivata deve implementare anche un metodo `Initialize` che non accetta argomenti e non restituisce alcun valore. Questo metodo non <xref:System.Configuration.SettingsProvider>è definito da .

 Infine, è <xref:System.Configuration.IApplicationSettingsProvider> possibile implementare nel provider per fornire il supporto per l'aggiornamento delle impostazioni, il ripristino delle impostazioni ai valori predefiniti e l'aggiornamento delle impostazioni da una versione dell'applicazione a un'altra.

 Dopo aver implementato e compilato il provider, è necessario istruire una classe di impostazioni affinché usi questo provider invece di quello predefinito. È possibile eseguire <xref:System.Configuration.SettingsProviderAttribute>questa operazione tramite il file . Se applicato a un'intera classe di impostazioni, il provider viene utilizzato per ogni impostazione definita dalla classe; Se applicata alle singole impostazioni, l'architettura Impostazioni applicazione <xref:System.Configuration.LocalFileSettingsProvider> utilizza tale provider solo per tali impostazioni e viene utilizzato per il resto. L'esempio di codice seguente illustra come indicare alla classe di impostazioni l'uso del provider personalizzato.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Un provider può essere chiamato da più thread contemporaneamente, ma scriverà sempre nello stesso percorso di archiviazione; pertanto l'architettura di Impostazioni applicazione creerà sempre una sola istanza della classe del provider.

> [!IMPORTANT]
> È necessario assicurarsi che il provider sia thread-safe e che consenta solo a un thread alla volta di scrivere i file di configurazione.

 Non è necessario che il provider supporti <xref:System.Configuration?displayProperty=nameWithType> tutti gli attributi delle impostazioni <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute>definiti nello spazio <xref:System.Configuration.DefaultSettingValueAttribute>dei nomi, sebbene sia supportato almeno e , e inoltre . Per gli attributi che non supporta, il provider deve semplicemente dare esito negativo senza notifica e non deve generare un'eccezione. Se la classe di impostazioni utilizza una combinazione non <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> valida di attributi, tuttavia, ad esempio l'applicazione e la stessa impostazione, il provider deve generare un'eccezione e interrompere l'operazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Panoramica delle impostazioni dell'applicazione](application-settings-overview.md)
- [Impostazioni delle applicazioni per i controlli personalizzati](application-settings-for-custom-controls.md)
- [ClickOnce e impostazioni dell'applicazione](/visualstudio/deployment/clickonce-and-application-settings)
- [Schema delle impostazioni delle applicazioni](../../configure-apps/file-schema/application-settings-schema.md)
