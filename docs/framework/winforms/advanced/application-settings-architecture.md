---
title: Architettura Impostazioni applicazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: c3858cfab59b63761f43f6b3eaad9bf8ca4c1dbc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916700"
---
# <a name="application-settings-architecture"></a>Architettura Impostazioni applicazione
Questo argomento descrive il funzionamento dell'architettura Impostazioni applicazione e ne analizza le funzionalità avanzate, come i raggruppamenti e le chiavi delle impostazioni.

 L'architettura di Impostazioni applicazione supporta la definizione delle impostazioni fortemente tipizzate con ambito di applicazione o utente e la persistenza delle impostazioni tra sessioni dell'applicazione. L'architettura fornisce un motore di persistenza predefinito per salvare le impostazioni e caricarle dal file system locale. L'architettura definisce inoltre le interfacce per offrire un motore di persistenza personalizzato.

 Si tratta di interfacce che consentono ai componenti personalizzati di mantenere le proprie impostazioni quando sono ospitati in un'applicazione. Usando le chiavi delle impostazioni, i componenti possono mantenere le impostazioni per più istanze del componente separato.

## <a name="defining-settings"></a>Definizione delle impostazioni
 L'architettura delle impostazioni dell'applicazione viene usata sia in ASP.NET che in Windows Forms e contiene un numero di classi di base condivise in entrambi gli ambienti. Il più importante è <xref:System.Configuration.SettingsBase>, che fornisce l'accesso alle impostazioni tramite una raccolta e fornisce metodi di basso livello per il caricamento e il salvataggio delle impostazioni. Ogni ambiente implementa la propria classe derivata da <xref:System.Configuration.SettingsBase> per fornire funzionalità di impostazioni aggiuntive per tale ambiente. In un'applicazione basata su Windows Forms, tutte le impostazioni dell'applicazione devono essere definite in una classe derivata <xref:System.Configuration.ApplicationSettingsBase> dalla classe, che aggiunge le funzionalità seguenti alla classe di base:

- Caricamento e salvataggio delle operazioni di livello superiore

- Supporto per le impostazioni con ambito utente

- Ripristino delle impostazioni dell'utente alle impostazioni predefinite

- Aggiornamento delle impostazioni da una versione precedente dell'applicazione

- Convalida delle impostazioni, prima che vengano modificate o prima che vengano salvate

 È possibile descrivere le impostazioni utilizzando diversi attributi definiti <xref:System.Configuration> nello spazio dei nomi, descritti in [attributi delle impostazioni dell'applicazione](application-settings-attributes.md). Quando si definisce un'impostazione, è necessario applicarla con <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, che descrive se l'impostazione si applica all'intera applicazione o solo all'utente corrente.

 L'esempio di codice seguente definisce una classe di impostazioni personalizzate con una singola impostazione, `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Persistenza delle impostazioni
 La <xref:System.Configuration.ApplicationSettingsBase> classe non mantiene le impostazioni o le impostazioni di caricamento; questo processo è associato al provider di impostazioni, una classe che <xref:System.Configuration.SettingsProvider>deriva da. Se una classe derivata di <xref:System.Configuration.ApplicationSettingsBase> non specifica un provider di impostazioni <xref:System.Configuration.SettingsProviderAttribute>tramite, viene utilizzato il provider predefinito, <xref:System.Configuration.LocalFileSettingsProvider>ovvero.

 Il sistema di configurazione rilasciato originariamente con il .NET Framework supporta la fornitura di dati statici di configurazione dell'applicazione tramite il file Machine. config del computer locale o `app.`all'interno di un file exe. config distribuito con applicazione. La <xref:System.Configuration.LocalFileSettingsProvider> classe espande il supporto nativo nei modi seguenti:

- Le impostazioni con ambito applicazione possono essere archiviate in entrambi i file machine.config o `app.`exe.config. Il file machine.config è sempre di sola lettura, mentre `app`.exe.config è limitato dalle considerazioni sulla sicurezza alla sola lettura per la maggior parte delle applicazioni.

- Le impostazioni con ambito di utente possono essere archiviate in `app`.exe.config, in questo caso vengono considerate come valori predefiniti statici.

- Le impostazioni con ambito di utente non predefinite sono archiviate in un nuovo file *utente*.config, dove *user* è il nome dell'utente che esegue l'applicazione in quel momento. È possibile specificare un valore predefinito per un'impostazione con ambito di utente <xref:System.Configuration.DefaultSettingValueAttribute>con. Poiché le impostazioni con ambito utente spesso cambiano durante l'esecuzione dell'applicazione, `user`.config è sempre di lettura o scrittura.

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

 È possibile associare solo un'impostazione dell'applicazione a un componente che supporta <xref:System.Windows.Forms.IBindableComponent> l'interfaccia. Inoltre, il componente deve implementare un evento di modifica per una proprietà associata specifica oppure notificare le impostazioni dell'applicazione che la proprietà è <xref:System.ComponentModel.INotifyPropertyChanged> stata modificata tramite l'interfaccia. Se il componente non implementa e <xref:System.Windows.Forms.IBindableComponent> si sta effettuando l'associazione tramite Visual Studio, le proprietà associate verranno impostate la prima volta, ma non verranno aggiornate. Se il componente implementa <xref:System.Windows.Forms.IBindableComponent> ma non supporta le notifiche delle modifiche delle proprietà, l'associazione non verrà aggiornata nel file di impostazioni quando la proprietà viene modificata.

 Alcuni componenti Windows Forms, ad esempio <xref:System.Windows.Forms.ToolStripItem>, non supportano le associazioni di impostazioni.

### <a name="settings-serialization"></a>Serializzazione delle impostazioni
 Quando <xref:System.Configuration.LocalFileSettingsProvider> è necessario salvare le impostazioni su disco, vengono eseguite le azioni seguenti:

1. Usa la reflection per esaminare tutte le proprietà definite nella <xref:System.Configuration.ApplicationSettingsBase> classe derivata, individuando quelle che vengono applicate <xref:System.Configuration.ApplicationScopedSettingAttribute> con o <xref:System.Configuration.UserScopedSettingAttribute>.

2. Serializza la proprietà su disco. Tenta innanzitutto di chiamare <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> o <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> sul tipo associato <xref:System.ComponentModel.TypeConverter>. Se il tentativo non riesce, usa la serializzazione XML.

3. Determina quali impostazioni vanno inserite in ciascun file, in base all'attributo dell'impostazione.

 Se si implementa una classe <xref:System.Configuration.SettingsSerializeAsAttribute> di impostazioni personalizzata, è possibile usare per contrassegnare un'impostazione per la serializzazione binaria o personalizzata usando l' <xref:System.Configuration.SettingsSerializeAs> enumerazione. Per ulteriori informazioni sulla creazione di una classe di impostazioni personalizzata nel codice [, vedere Procedura: Creare le impostazioni](how-to-create-application-settings.md)dell'applicazione.

### <a name="settings-file-locations"></a>Percorsi dei file delle impostazioni
 Il percorso dei file `app`.exe.config e *user*.config variano in base alle modalità di installazione dell'applicazione. Per un'applicazione basata su Windows Forms copiata nel computer locale, `app`. exe. config si troverà nella stessa directory della directory di base del file eseguibile principale dell'applicazione e *User*. config si troverà nel percorso specificato da <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> proprietà. Per un'applicazione installata per mezzo di ClickOnce, entrambi questi file si troveranno nella directory dei dati ClickOnce sotto%InstallRoot%\\Documents e impostazioni\\*nome utente*\Impostazioni impostazioni.

 Il percorso di archiviazione di questi file è leggermente diverso se un utente ha abilitato i profili di roaming, che consentono all'utente di definire diverse impostazioni di Windows e dell'applicazione quando usa altri computer all'interno di un dominio. In tal caso, sia le applicazioni ClickOnce che le applicazioni non `app`ClickOnce avranno i file exe. config e *User*. config archiviati in%InstallRoot%\\Documents e Settings\\*nomeutente*\Dati.

 Per altre informazioni sul funzionamento delle funzioni di Impostazioni applicazione con la nuova tecnologia di distribuzione, vedere [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings). Per ulteriori informazioni sulla directory dei dati ClickOnce, vedere [accesso a dati locali e remoti in applicazioni ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).

## <a name="application-settings-and-security"></a>Impostazioni e sicurezza dell'applicazione
 Le impostazioni dell'applicazione sono progettate per funzionare in attendibilità parziale, un ambiente con restrizioni predefinito per le applicazioni di Windows Form ospitate in Internet o intranet. Non sono necessarie autorizzazioni speciali oltre all'attendibilità parziale per usare le impostazioni dell'applicazione con il provider di impostazioni predefinito.

 Quando si utilizzano le impostazioni dell'applicazione in un'applicazione ClickOnce `user`, il file config viene archiviato nella directory dei dati ClickOnce. Le dimensioni del file `user`. config dell'applicazione non possono superare la quota di directory dati impostata da ClickOnce. Per altre informazioni, vedere [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Provider di impostazioni personalizzate
 Nell'architettura delle impostazioni dell'applicazione è presente un accoppiamento libero tra la classe wrapper delle impostazioni delle applicazioni, <xref:System.Configuration.ApplicationSettingsBase>derivata da, e il provider o i provider di impostazioni <xref:System.Configuration.SettingsProvider>associate, derivati da. Questa associazione viene definita solo dall'oggetto <xref:System.Configuration.SettingsProviderAttribute> applicato alla classe wrapper o alle sue singole proprietà. Se un provider di impostazioni non viene specificato in modo esplicito, viene <xref:System.Configuration.LocalFileSettingsProvider>utilizzato il provider predefinito. Di conseguenza, questa architettura supporta la creazione e l'uso di provider di impostazioni personalizzate.

 Si supponga, ad esempio, di voler sviluppare e usare `SqlSettingsProvider`, un provider che archivierà tutti i dati delle impostazioni in un database Microsoft SQL Server. La <xref:System.Configuration.SettingsProvider>classe derivata da riceve queste informazioni `Initialize` nel metodo come parametro di tipo <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>. Implementare quindi il <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> metodo per recuperare le impostazioni dall'archivio dati e <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> per salvarle. Il provider può utilizzare l' <xref:System.Configuration.SettingsPropertyCollection> oggetto fornito <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> a per determinare il nome, il tipo e l'ambito della proprietà, nonché gli eventuali altri attributi delle impostazioni definiti per la proprietà.

 Il provider dovrà implementare una proprietà e un metodo le cui implementazioni possono non essere evidenti. La <xref:System.Configuration.SettingsProvider.ApplicationName%2A> proprietà è una proprietà astratta di <xref:System.Configuration.SettingsProvider>. è necessario programmarla per restituire gli elementi seguenti:

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 La classe derivata deve implementare anche un metodo `Initialize` che non accetta argomenti e non restituisce alcun valore. Questo metodo non è definito da <xref:System.Configuration.SettingsProvider>.

 Infine, si implementa <xref:System.Configuration.IApplicationSettingsProvider> nel provider per fornire supporto per l'aggiornamento delle impostazioni, il ripristino delle impostazioni predefinite e l'aggiornamento delle impostazioni da una versione dell'applicazione a un'altra.

 Dopo aver implementato e compilato il provider, è necessario istruire una classe di impostazioni affinché usi questo provider invece di quello predefinito. A tale <xref:System.Configuration.SettingsProviderAttribute>scopo, è possibile usare. Se applicato a un'intera classe di impostazioni, il provider viene usato per ogni impostazione definita dalla classe; Se applicato a singole impostazioni, l'architettura delle impostazioni dell'applicazione usa tale provider solo per queste impostazioni <xref:System.Configuration.LocalFileSettingsProvider> e USA per il resto. L'esempio di codice seguente illustra come indicare alla classe di impostazioni l'uso del provider personalizzato.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Un provider può essere chiamato da più thread contemporaneamente, ma scriverà sempre nello stesso percorso di archiviazione; pertanto l'architettura di Impostazioni applicazione creerà sempre una sola istanza della classe del provider.

> [!IMPORTANT]
> È necessario assicurarsi che il provider sia thread-safe e che consenta solo a un thread alla volta di scrivere i file di configurazione.

 Non è necessario che il provider supporti tutti gli attributi <xref:System.Configuration?displayProperty=nameWithType> delle impostazioni definiti nello spazio dei nomi, anche se deve supportare almeno <xref:System.Configuration.ApplicationScopedSettingAttribute> e <xref:System.Configuration.UserScopedSettingAttribute>e deve supportare <xref:System.Configuration.DefaultSettingValueAttribute>. Per gli attributi che non supporta, il provider deve semplicemente dare esito negativo senza notifica e non deve generare un'eccezione. Se la classe Settings usa una combinazione di attributi non valida, tuttavia, ad esempio <xref:System.Configuration.ApplicationScopedSettingAttribute> applicando e <xref:System.Configuration.UserScopedSettingAttribute> alla stessa impostazione, il provider deve generare un'eccezione e interrompere l'operazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
- [Application Settings for Custom Controls](application-settings-for-custom-controls.md)
- [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings)
- [Schema Application Settings](../../configure-apps/file-schema/application-settings-schema.md)
