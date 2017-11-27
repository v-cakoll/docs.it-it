---
title: Stringhe di connessione e file di configurazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 37df2641-661e-407a-a3fb-7bf9540f01e8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fe56dc279471f77a3f9ae014f65faaa99a113624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-and-configuration-files"></a>Stringhe di connessione e file di configurazione
Se le stringhe di connessione vengono incorporate nel codice dell'applicazione, è possibile che si verifichino vulnerabilità della sicurezza e problemi di manutenzione. È possibile visualizzare le stringhe di connessione non crittografata compilate nel codice sorgente di un'applicazione utilizzando il [Ildasm.exe (Disassembler IL)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) strumento. Inoltre, se la stringa di connessione viene modificata, è necessario ricompilare l'applicazione. Per questi motivi, si consiglia di archiviare le stringhe di connessione in un file di configurazione dell'applicazione.  
  
## <a name="working-with-application-configuration-files"></a>Utilizzo dei file di configurazione delle applicazioni  
 I file di configurazione delle applicazioni contengono impostazioni specifiche di una determinata applicazione. Ad esempio, un'applicazione ASP.NET può avere uno o più **Web. config** file e un'applicazione Windows può avere un parametro facoltativo **app** file. I file di configurazione condividono elementi comuni, anche se il nome e il percorso variano a seconda dell'host dell'applicazione.  
  
### <a name="the-connectionstrings-section"></a>Sezione connectionStrings  
 Le stringhe di connessione possono essere archiviate come coppie chiave/valore nel **connectionStrings** sezione la **configurazione** elemento di un file di configurazione dell'applicazione. Gli elementi figlio includono **aggiungere**, **deselezionare**, e **rimuovere**.  
  
 Nel frammento di file di configurazione seguente sono illustrati lo schema e la sintassi per l'archiviazione di una stringa di connessione. Il **nome** attributo è un nome specificato per identificare in modo univoco una stringa di connessione in modo che possa essere recuperato in fase di esecuzione. Il **providerName** è il nome invariante del provider di dati .NET Framework, viene registrato nel file Machine. config.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
  <configuration>  
    <connectionStrings>  
      <clear />  
      <add name="Name"   
       providerName="System.Data.ProviderName"   
       connectionString="Valid Connection String;" />  
    </connectionStrings>  
  </configuration>  
```  
  
> [!NOTE]
>  È possibile salvare parte di una stringa di connessione in un file di configurazione e usare la classe <xref:System.Data.Common.DbConnectionStringBuilder> per completarlo in fase di esecuzione. Questa funzione è utile nelle situazioni in cui non si conoscono in anticipo gli elementi della stringa di connessione o quando non si desidera salvare informazioni sensibili in un file di configurazione. Per ulteriori informazioni, vedere [generatori di stringhe di connessione](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
### <a name="using-external-configuration-files"></a>Uso di file di configurazione esterni  
 I file di configurazione esterni sono file distinti che contengono un frammento di un file di configurazione costituito da un'unica sezione. Al file di configurazione esterno viene quindi fatto riferimento dal file di configurazione principale. L'archiviazione di **connectionStrings** sezione in un file fisicamente distinto risulta utile nelle situazioni in cui le stringhe di connessione possono essere modificate dopo l'applicazione viene distribuita. Ad esempio, il comportamento ASP.NET standard prevede il riavvio di un dominio di applicazione quando i file di configurazione vengono modificati, con la conseguenza che le informazioni sullo stato vanno perse. Tuttavia, la modifica di un file di configurazione esterno non provoca un riavvio dell'applicazione. Oltre che in ASP.NET, i file di configurazione esterni possono essere usati anche nelle applicazioni Windows. È possibile inoltre usare la sicurezza e le autorizzazioni di accesso ai file per limitare l'accesso ai file di configurazione esterni. L'uso di file di configurazione esterni in fase di esecuzione è trasparente e non richiede codice speciale.  
  
 Per archiviare le stringhe di connessione nel file di configurazione esterno, creare un file distinto che contiene solo il **connectionStrings** sezione. Non includere altri elementi, sezioni o attributi. Questo esempio illustra la sintassi di un file di configurazione esterno.  
  
```xml  
<connectionStrings>  
  <add name="Name"   
   providerName="System.Data.ProviderName"   
   connectionString="Valid Connection String;" />  
</connectionStrings>  
```  
  
 Nel file di configurazione principale dell'applicazione, utilizzare il **configSource** attributo per specificare il nome completo e il percorso del file esterno. In questo esempio si fa riferimento a un file di configurazione esterno denominato `connections.config`.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
<configuration>  
    <connectionStrings configSource="connections.config"/>  
</configuration>  
```  
  
## <a name="retrieving-connection-strings-at-run-time"></a>Recupero delle stringhe di connessione in fase di esecuzione  
 In .NET Framework 2.0 sono state introdotte nuove classi nello spazio dei nomi <xref:System.Configuration> per semplificare il recupero delle stringhe di connessione dai file di configurazione in fase di esecuzione. È possibile recuperare una stringa di connessione a livello di codice in base al nome o al nome del provider.  
  
> [!NOTE]
>  Il **Machine. config** file contiene inoltre un **connectionStrings** sezione che contiene stringhe di connessione utilizzate da Visual Studio. Durante il recupero di stringhe di connessione dal nome del provider di **app** in un'applicazione Windows, le stringhe di connessione nel file **Machine. config** ottenere prima di caricare e successivamente le voci da **app**. Aggiunta di **deselezionare** immediatamente dopo il **connectionStrings** elemento rimuove tutti i riferimenti ereditati dalla struttura di dati in memoria, in modo che solo le stringhe di connessione definite locale **app** vengono considerati file.  
  
### <a name="working-with-the-configuration-classes"></a>Utilizzo delle classi di configurazione  
 A partire da .NET Framework 2.0, quando si usano i file di configurazione nel computer locale, viene usato <xref:System.Configuration.ConfigurationManager> al posto dell'oggetto <xref:System.Configuration.ConfigurationSettings> deprecato. Per i file di configurazione di ASP.NET, viene usato <xref:System.Web.Configuration.WebConfigurationManager>, È progettato per funzionare con i file di configurazione in un server Web e consente l'accesso programmatico alle sezioni di file di configurazione, ad esempio **System. Web**.  
  
> [!NOTE]
>  L'accesso ai file di configurazione in fase di esecuzione richiede la concessione di autorizzazioni al chiamante. Le autorizzazioni necessarie dipendono dal tipo di applicazione, dal file di configurazione e dal percorso. Per ulteriori informazioni, vedere [utilizzando le classi di configurazione](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc) e <xref:System.Web.Configuration.WebConfigurationManager> per le applicazioni ASP.NET, e <xref:System.Configuration.ConfigurationManager> per le applicazioni di Windows.  
  
 È possibile usare <xref:System.Configuration.ConnectionStringSettingsCollection> per recuperare le stringhe di connessione dai file di configurazione dell'applicazione. Contiene una raccolta di <xref:System.Configuration.ConnectionStringSettings> oggetti, ognuno dei quali rappresenta una singola voce di **connectionStrings** sezione. Le proprietà sono mappate ad attributi di stringa di connessione, consentendo di recuperare una stringa di connessione in base al nome o al nome del provider.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Configuration.ConnectionStringSettings.Name%2A>|Nome della stringa di connessione. Esegue il mapping al **nome** attributo.|  
|<xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>|Nome completo del provider. Esegue il mapping al **providerName** attributo.|  
|<xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A>|Stringa di connessione. Esegue il mapping al **connectionString** attributo.|  
  
### <a name="example-listing-all-connection-strings"></a>Esempio: elenco di tutte le stringhe di connessione  
 In questo esempio viene scorsa la raccolta `ConnectionStringSettings` e vengono visualizzate le proprietà <xref:System.Configuration.ConnectionStringSettings.Name%2A>, <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> e <xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A> nella finestra della console.  
  
> [!NOTE]
>  System.Configuration.dll non è incluso in tutti i tipi di progetto e potrebbe essere necessario impostare un riferimento a questo file per usare le classi di configurazione. Il nome e il percorso di un determinato file di configurazione dell'applicazione variano in base al tipo di applicazione e al processo di hosting.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-name"></a>Esempio: recupero di una stringa di connessione in base al nome  
 In questo esempio viene illustrato come recuperare una stringa di connessione da un file di configurazione specificandone il nome. Nel codice viene creato un oggetto <xref:System.Configuration.ConnectionStringSettings> e il parametro di input specificato viene associato al nome <xref:System.Configuration.ConfigurationManager.ConnectionStrings%2A>. Se non viene trovato alcun nome corrispondente, la funzione restituisce `null` (`Nothing` in Visual Basic).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-provider-name"></a>Esempio: recupero di una stringa di connessione in base al nome del provider  
 In questo esempio viene illustrato come recuperare una stringa di connessione specificando il nome invariabile del provider nel formato *ProviderName*. Il codice consente di scorrere <xref:System.Configuration.ConnectionStringSettingsCollection> e restituisce la stringa di connessione per il primo <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> trovato. Se il nome del provider non viene trovato, la funzione restituisce `null` (`Nothing` in Visual Basic).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="encrypting-configuration-file-sections-using-protected-configuration"></a>Crittografia di sezioni dei file di configurazione tramite configurazione protetta  
 ASP.NET 2.0 ha introdotto una nuova funzionalità, denominata *la configurazione protetta*, che consente di crittografare le informazioni riservate in un file di configurazione. Sebbene sia stata progettata principalmente per ASP.NET, questa funzionalità può essere usata anche per crittografare sezioni dei file di configurazione nelle applicazioni Windows. Per una descrizione dettagliata delle funzionalità di configurazione protetta, vedere [crittografia configurazione informazioni tramite configurazione protetta](http://msdn.microsoft.com/library/51cdfe5b-9d82-458c-94ff-c551c4f38ed1).  
  
 Frammento di file di configurazione seguente viene illustrato il **connectionStrings** sezione dopo che è stato crittografato. Il **configProtectionProvider** specifica il provider di configurazione protetta usato per crittografare e decrittografare le stringhe di connessione. Il **EncryptedData** sezione contiene il testo crittografato.  
  
```xml  
<connectionStrings configProtectionProvider="DataProtectionConfigurationProvider">  
  <EncryptedData>  
    <CipherData>  
      <CipherValue>AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAH2... </CipherValue>  
    </CipherData>  
  </EncryptedData>  
</connectionStrings>  
```  
  
 Quando la stringa di connessione crittografata viene recuperata in fase di esecuzione, .NET Framework Usa il provider specificato per decrittografare il **CipherValue** e renderlo disponibile per l'applicazione. Non è necessario scrivere codice aggiuntivo per gestire il processo di decrittografia.  
  
### <a name="protected-configuration-providers"></a>Provider di configurazione protetta  
 Provider di configurazione protetta sono registrati nel **configProtectedData** sezione la **Machine. config** file nel computer locale, come illustrato nel frammento seguente, che mostra le due provider di configurazione protetta fornito con .NET Framework. I valori mostrati sono stati troncati per facilitarne la lettura.  
  
```xml  
<configProtectedData defaultProvider="RsaProtectedConfigurationProvider">  
  <providers>  
    <add name="RsaProtectedConfigurationProvider"   
      type="System.Configuration.RsaProtectedConfigurationProvider, ... />  
    <add name="DataProtectionConfigurationProvider"   
      type="System.Configuration.DpapiProtectedConfigurationProvider, ... />  
  </providers>  
</configProtectedData>  
```  
  
 È possibile configurare il provider di aggiuntive di configurazione protetta aggiungendoli al file il **Machine. config** file. È inoltre possibile creare un proprio provider di configurazione protetta ereditando dalla classe base astratta <xref:System.Configuration.ProtectedConfigurationProvider>. La tabella seguente descrive i due file di configurazione inclusi in .NET Framework.  
  
|Provider|Descrizione|  
|--------------|-----------------|  
|<!--zz<xref:System.Configuration.RSAProtectedConfigurationProvider>-->`System.Configuration.RSAProtectedConfigurationProvider`|Usa l'algoritmo di crittografia RSA per crittografare e decrittografare i dati. L'algoritmo RSA può essere usato per la crittografia a chiave pubblica e per le firme digitali. È anche noto come crittografia a "chiave pubblica" o asimmetrica perché impiega due chiavi diverse. È possibile utilizzare il [strumento di registrazione ASP.NET IIS (Aspnet_regiis.exe)](http://msdn.microsoft.com/library/6491c41e-e2b0-481f-9863-db3614d5f96b) per crittografare le sezioni in un file Web. config e gestire le chiavi di crittografia. In ASP.NET il file di configurazione viene decrittografato al momento dell'elaborazione. L'identità dell'applicazione ASP.NET deve disporre di accesso in lettura alla chiave di crittografia usata per crittografare e decrittografare le sezioni crittografate.|  
|<!--zz<xref:System.Configuration.DPAPIProtectedConfigurationProvider>-->`System.Configuration.DPAPIProtectedConfigurationProvider`|Usa DPAPI (Data Protection API) di Windows per crittografare le sezioni di configurazione. Usa i servizi di crittografia incorporati di Windows e può essere configurato per la protezione specifica del computer o specifica dell'account utente. La protezione specifica del computer risulta utile quando più applicazioni sullo stesso server devono condividere informazioni. La protezione specifica dell'account utente può essere usata con i servizi eseguiti con un'identità utente specifica, ad esempio un ambiente di hosting condiviso. Ogni applicazione viene eseguita con un'identità distinta, limitando l'accesso a risorse quali file e database.|  
  
 Entrambi i provider offrono una crittografia avanzata per i dati. Se tuttavia si prevede di usare lo stesso file di configurazione crittografato in più server, ad esempio una Web farm, solo `RsaProtectedConfigurationProvider` consente di esportare le chiavi di crittografia usate per crittografare i dati e importarle in un altro server. Per ulteriori informazioni, vedere [importazione ed esportazione protetto configurazione contenitori di chiavi RSA](http://msdn.microsoft.com/library/f3022b39-f17f-48c1-b067-025eab0ce8bc).  
  
### <a name="using-the-configuration-classes"></a>Utilizzo delle classi di configurazione  
 Lo spazio dei nomi <xref:System.Configuration> fornisce classi per specificare le impostazioni di configurazione a livello di codice. La classe <xref:System.Configuration.ConfigurationManager> fornisce accesso a file di configurazione del computer, dell'applicazione e dell'utente. Se si sta creando un'applicazione ASP.NET, è possibile utilizzare il <xref:System.Web.Configuration.WebConfigurationManager> (classe), che fornisce la stessa funzionalità mentre permette di accedere alle impostazioni che sono univoche per le applicazioni ASP.NET, ad esempio quelli trovati  **\< System. Web >**.  
  
> [!NOTE]
>  Lo spazio dei nomi <xref:System.Security.Cryptography> contiene classi che forniscono opzioni aggiuntive per la crittografia e la decrittografia dei dati. Usare queste classi se si richiedono servizi di crittografia che non sono disponibili tramite configurazione protetta. In alcuni casi si tratta di wrapper presenti nelle CryptoAPI di Microsoft non gestite, in altri semplicemente di implementazioni gestite. Per ulteriori informazioni, vedere [servizi di crittografia](http://msdn.microsoft.com/en-us/68a1e844-c63c-44af-9247-f6716eb23781).  
  
### <a name="appconfig-example"></a>Esempio di App.config  
 In questo esempio viene illustrato come attivare o disattivare la crittografia di **connectionStrings** sezione un **app** file per un'applicazione Windows. La procedura assume il nome dell'applicazione come argomento, ad esempio "MyApplication.exe". Il **app** file verrà quindi crittografato e copiato nella cartella che contiene il file eseguibile con il nome "MyApplication.exe".  
  
> [!NOTE]
>  La stringa di connessione può essere decrittografata solo nel computer in cui è stata crittografata.  
  
 Il codice Usa il <xref:System.Configuration.ConfigurationManager.OpenExeConfiguration%2A> per aprire la **app. config** file per la modifica e <xref:System.Configuration.ConfigurationManager.GetSection%2A> metodo restituisce il **connectionStrings** sezione. Viene quindi controllata la proprietà <xref:System.Configuration.SectionInformation.IsProtected%2A>, con una chiamata a <xref:System.Configuration.SectionInformation.ProtectSection%2A> per crittografare la sezione, se non è crittografata. Il metodo <xref:System.Configuration.SectionInformation.UnprotectSection%2A> viene richiamato per decrittografare la sezione. Il metodo <xref:System.Configuration.Configuration.Save%2A> completa l'operazione e salva le modifiche.  
  
> [!NOTE]
>  È necessario impostare un riferimento a `System.Configuration.dll` nel progetto affinché il codice venga eseguito.  
  
 [!code-csharp[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/VB/source.vb#1)]  
  
### <a name="webconfig-example"></a>Esempio di Web.config  
 In questo esempio viene usato il metodo <xref:System.Web.Configuration.WebConfigurationManager.OpenWebConfiguration%2A> di `WebConfigurationManager`. Si noti che in questo caso è possibile specificare il percorso relativo di **Web. config** file usando una tilde. Il codice richiede un riferimento alla classe `System.Web.Configuration`.  
  
 [!code-csharp[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/VB/source.vb#1)]  
  
 Per altre informazioni di protezione delle applicazioni ASP.NET, vedere [NIB: sicurezza ASP.NET](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d) e [consigliate per la sicurezza ASP.NET 2.0 a colpo d'occhio](http://go.microsoft.com/fwlink/?LinkId=59997) in ASP.NET Developer Center.  
  
## <a name="see-also"></a>Vedere anche  
 [Generatori di stringhe di connessione](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Utilizzo delle classi di configurazione](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [Configurazione di applicazioni](../../../../docs/framework/configure-apps/index.md)  
 [Amministrazione sito Web ASP.NET](http://msdn.microsoft.com/library/1298034b-5f7d-464d-abd1-ad9e6b3eeb7e)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
