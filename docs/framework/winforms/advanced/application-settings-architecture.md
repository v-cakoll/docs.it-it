---
title: Architettura Impostazioni applicazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: c2a62b61cb7b31c978a84a3d3f41c24f9fafb84d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312566"
---
# <a name="application-settings-architecture"></a>Architettura Impostazioni applicazione
Questo argomento descrive il funzionamento dell'architettura Impostazioni applicazione e ne analizza le funzionalità avanzate, come i raggruppamenti e le chiavi delle impostazioni.  
  
 L'architettura di Impostazioni applicazione supporta la definizione delle impostazioni fortemente tipizzate con ambito di applicazione o utente e la persistenza delle impostazioni tra sessioni dell'applicazione. L'architettura fornisce un motore di persistenza predefinito per salvare le impostazioni e caricarle dal file system locale. L'architettura definisce inoltre le interfacce per offrire un motore di persistenza personalizzato.  
  
 Si tratta di interfacce che consentono ai componenti personalizzati di mantenere le proprie impostazioni quando sono ospitati in un'applicazione. Usando le chiavi delle impostazioni, i componenti possono mantenere le impostazioni per più istanze del componente separato.  
  
## <a name="defining-settings"></a>Definizione delle impostazioni  
 L'architettura delle impostazioni applicazione viene usata sia in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] che in Windows Form e contiene un numero di classi di base condivise in entrambi gli ambienti. La più importante è <xref:System.Configuration.SettingsBase>, fornisce l'accesso alle impostazioni attraverso una raccolta che fornisce metodi di basso livello per il caricamento e salvataggio delle impostazioni. Ogni ambiente implementa una propria classe derivata da <xref:System.Configuration.SettingsBase> per fornire funzionalità aggiuntive delle impostazioni per quell'ambiente. In un'applicazione basata su Windows Form, tutte le impostazioni dell'applicazione devono essere definite in una classe derivata dal <xref:System.Configuration.ApplicationSettingsBase> (classe), che consente di aggiungere le funzionalità seguenti alla classe di base:  
  
-   Caricamento e salvataggio delle operazioni di livello superiore  
  
-   Supporto per le impostazioni con ambito utente  
  
-   Ripristino delle impostazioni dell'utente alle impostazioni predefinite  
  
-   Aggiornamento delle impostazioni da una versione precedente dell'applicazione  
  
-   Convalida delle impostazioni, prima che vengano modificate o prima che vengano salvate  
  
 Le impostazioni possono essere descritte usando una serie di attributi definiti all'interno di <xref:System.Configuration> dello spazio dei nomi; questi sono descritti nella [Application Settings Attributes](application-settings-attributes.md). Quando si definisce un'impostazione, è necessario applicarlo con uno <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, che descrive se l'impostazione si applica all'intera applicazione o semplicemente per l'utente corrente.  
  
 L'esempio di codice seguente definisce una classe di impostazioni personalizzate con una singola impostazione, `BackgroundColor`.  
  
 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## <a name="settings-persistence"></a>Persistenza delle impostazioni  
 Il <xref:System.Configuration.ApplicationSettingsBase> classe non mantiene o carica le impostazioni; tale operazione è effettuata dal provider di impostazioni, una classe che deriva da <xref:System.Configuration.SettingsProvider>. Se una classe derivata di <xref:System.Configuration.ApplicationSettingsBase> non specifica un provider di impostazioni tramite i <xref:System.Configuration.SettingsProviderAttribute>, quindi il provider predefinito, <xref:System.Configuration.LocalFileSettingsProvider>, viene usato.  
  
 Il sistema di configurazione che è stato rilasciato originariamente con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] supporta l'offerta di dati di configurazione dell'applicazione statici tramite file machine.config del computer locale o in un file `app.`.exe.config da distribuire con l'applicazione. Il <xref:System.Configuration.LocalFileSettingsProvider> classe espande tale supporto nativo nei modi seguenti:  
  
-   Le impostazioni con ambito applicazione possono essere archiviate in entrambi i file machine.config o `app.`exe.config. Il file machine.config è sempre di sola lettura, mentre `app`.exe.config è limitato dalle considerazioni sulla sicurezza alla sola lettura per la maggior parte delle applicazioni.  
  
-   Le impostazioni con ambito di utente possono essere archiviate in `app`.exe.config, in questo caso vengono considerate come valori predefiniti statici.  
  
-   Le impostazioni con ambito di utente non predefinite sono archiviate in un nuovo file *utente*.config, dove *user* è il nome dell'utente che esegue l'applicazione in quel momento. È possibile specificare un valore predefinito per un'impostazione con ambito di utente con <xref:System.Configuration.DefaultSettingValueAttribute>. Poiché le impostazioni con ambito utente spesso cambiano durante l'esecuzione dell'applicazione, `user`.config è sempre di lettura o scrittura.  
  
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
  
 È possibile associare solo un'impostazione dell'applicazione a un componente che supporta il <xref:System.Windows.Forms.IBindableComponent> interfaccia. Inoltre, il componente deve implementare un evento di modifica per una specifica proprietà associata o notificare le impostazioni dell'applicazione che la proprietà viene modificata tramite il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Se il componente non implementa <xref:System.Windows.Forms.IBindableComponent> e si desidera associare tramite Visual Studio, le proprietà associate verranno impostate la prima volta, ma non verranno aggiornato. Se il componente implementa <xref:System.Windows.Forms.IBindableComponent> ma le notifiche di modifica non proprietà di supporto, l'associazione non verrà aggiornata nel file di impostazioni quando la proprietà viene modificata.  
  
 Alcuni componenti di Windows Form, ad esempio <xref:System.Windows.Forms.ToolStripItem>, non supportano le associazioni delle impostazioni.  
  
### <a name="settings-serialization"></a>Serializzazione delle impostazioni  
 Quando <xref:System.Configuration.LocalFileSettingsProvider> deve salvare le impostazioni su disco, esegue le azioni seguenti:  
  
1. Usa la reflection per esaminare tutte le proprietà definite per il <xref:System.Configuration.ApplicationSettingsBase> trovando quelle che vengono applicate con la classe derivata <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>.  
  
2. Serializza la proprietà su disco. Innanzitutto tenta di chiamare il <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> oppure <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> su associato al tipo <xref:System.ComponentModel.TypeConverter>. Se il tentativo non riesce, usa la serializzazione XML.  
  
3. Determina quali impostazioni vanno inserite in ciascun file, in base all'attributo dell'impostazione.  
  
 Se si implementa una propria classe di impostazioni, è possibile usare la <xref:System.Configuration.SettingsSerializeAsAttribute> per contrassegnare un'impostazione per la serializzazione binaria o personalizzata usando il <xref:System.Configuration.SettingsSerializeAs> enumerazione. Per altre informazioni sulla creazione di una propria classe di impostazioni nel codice, vedere [come: Creare le impostazioni dell'applicazione](how-to-create-application-settings.md).  
  
### <a name="settings-file-locations"></a>Percorsi dei file delle impostazioni  
 Il percorso dei file `app`.exe.config e *user*.config variano in base alle modalità di installazione dell'applicazione. Per un'applicazione basata su Windows Form copiata nel computer locale, `app`. exe. config si trovi nella stessa directory della directory di base del file eseguibile principale dell'applicazione, e *utente*. config si troverà di percorso specificato da di <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> proprietà. Per un'applicazione installata tramite [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], entrambi questi file si troveranno nella Directory dati [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] %InstallRoot%\Documents e Impostazioni\\*nome utente*\Impostazioni locali.  
  
 Il percorso di archiviazione di questi file è leggermente diverso se un utente ha abilitato i profili di roaming, che consentono all'utente di definire diverse impostazioni di Windows e dell'applicazione quando usa altri computer all'interno di un dominio. In tal caso, sia le applicazioni [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] che quelle diverse da [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] dispongono dei propri file `app`.exe.config e *user*.config archiviati in %InstallRoot%\Documenti e Impostazioni\\*nome utente*\Application Data.  
  
 Per altre informazioni sul funzionamento delle funzioni di Impostazioni applicazione con la nuova tecnologia di distribuzione, vedere [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings). Per altre informazioni sulla directory dei dati [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], vedere [Accesso a dati locali e remoti in applicazioni ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).  
  
## <a name="application-settings-and-security"></a>Impostazioni e sicurezza dell'applicazione  
 Le impostazioni dell'applicazione sono progettate per funzionare in attendibilità parziale, un ambiente con restrizioni predefinito per le applicazioni di Windows Form ospitate in Internet o intranet. Non sono necessarie autorizzazioni speciali oltre all'attendibilità parziale per usare le impostazioni dell'applicazione con il provider di impostazioni predefinito.  
  
 Quando si usano le impostazioni dell'applicazione in un'applicazione [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], il file `user`.config è archiviato nella directory dei dati di [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]. Le dimensioni del file `user`.config dell'applicazione non possono superare la quota della directory dei dati impostata da [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]. Per altre informazioni, vedere [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings).  
  
## <a name="custom-settings-providers"></a>Provider di impostazioni personalizzate  
 Nell'architettura di impostazioni dell'applicazione, è un accoppiamento libero tra le impostazioni di applicazioni classi wrapper, derivato da <xref:System.Configuration.ApplicationSettingsBase>, e il provider di impostazioni associato o il provider, derivato da <xref:System.Configuration.SettingsProvider>. Questa associazione viene definita solo per il <xref:System.Configuration.SettingsProviderAttribute> applicato alla classe wrapper o alle singole proprietà. Se le impostazioni di un provider non è esplicitamente specificata, il provider predefinito, <xref:System.Configuration.LocalFileSettingsProvider>, viene usato. Di conseguenza, questa architettura supporta la creazione e l'uso di provider di impostazioni personalizzate.  
  
 Si supponga, ad esempio, di voler sviluppare e usare `SqlSettingsProvider`, un provider che archivierà tutti i dati delle impostazioni in un database Microsoft SQL Server. I <xref:System.Configuration.SettingsProvider>-classe derivata riceve queste informazioni nel relativo `Initialize` metodo come parametro di tipo <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>. È quindi necessario implementare il <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> metodo per recuperare le impostazioni dall'archivio dati, e <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> salvarle. Il provider può usare la <xref:System.Configuration.SettingsPropertyCollection> fornito a <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> per determinare la proprietà nome tipo e ambito, nonché eventuali attributi delle impostazioni definiti per tale proprietà.  
  
 Il provider dovrà implementare una proprietà e un metodo le cui implementazioni possono non essere evidenti. Il <xref:System.Configuration.SettingsProvider.ApplicationName%2A> è una proprietà astratta di <xref:System.Configuration.SettingsProvider>; è necessario programmarla affinché restituisca quanto segue:  
  
 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 La classe derivata deve implementare anche un metodo `Initialize` che non accetta argomenti e non restituisce alcun valore. Questo metodo non è definito da <xref:System.Configuration.SettingsProvider>.  
  
 Infine, implementa <xref:System.Configuration.IApplicationSettingsProvider> sul provider per fornire il supporto per l'aggiornamento delle impostazioni, il ripristino dei valori predefiniti e l'aggiornamento dalla versione di un'applicazione a un altro.  
  
 Dopo aver implementato e compilato il provider, è necessario istruire una classe di impostazioni affinché usi questo provider invece di quello predefinito. Eseguire tale operazione mediante la <xref:System.Configuration.SettingsProviderAttribute>. Se applicato a un'intera classe di impostazioni, viene utilizzato il provider per ogni impostazione che definisce la classe; Se applicato a singole impostazioni, architettura Impostazioni applicazione usa il provider solo per determinate impostazioni e Usa <xref:System.Configuration.LocalFileSettingsProvider> per il resto. L'esempio di codice seguente illustra come indicare alla classe di impostazioni l'uso del provider personalizzato.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 Un provider può essere chiamato da più thread contemporaneamente, ma scriverà sempre nello stesso percorso di archiviazione; pertanto l'architettura di Impostazioni applicazione creerà sempre una sola istanza della classe del provider.  
  
> [!IMPORTANT]
>  È necessario assicurarsi che il provider sia thread-safe e che consenta solo a un thread alla volta di scrivere i file di configurazione.  
  
 Il provider non è necessario supportare tutte le impostazioni di attributi definiti nel <xref:System.Configuration?displayProperty=nameWithType> dello spazio dei nomi, ma deve un supporto minimo <xref:System.Configuration.ApplicationScopedSettingAttribute> e <xref:System.Configuration.UserScopedSettingAttribute>e deve anche supportare <xref:System.Configuration.DefaultSettingValueAttribute>. Per gli attributi che non supporta, il provider deve semplicemente dare esito negativo senza notifica e non deve generare un'eccezione. Se la classe delle impostazioni utilizza una combinazione non valida di attributi, tuttavia, quali l'applicazione <xref:System.Configuration.ApplicationScopedSettingAttribute> e <xref:System.Configuration.UserScopedSettingAttribute> alla stessa impostazione, il provider deve generare un'eccezione e annullare l'operazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
- [Application Settings for Custom Controls](application-settings-for-custom-controls.md)
- [Impostazioni dell'applicazione e ClickOnce](/visualstudio/deployment/clickonce-and-application-settings)
- [Schema Application Settings](../../configure-apps/file-schema/application-settings-schema.md)
