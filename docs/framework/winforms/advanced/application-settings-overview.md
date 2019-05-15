---
title: Cenni preliminari sulle impostazioni delle applicazioni
ms.date: 03/30/2017
f1_keywords:
- ApplicationsSettingsOverview
helpviewer_keywords:
- application settings [Windows Forms], about application settings
- dynamic properties
- user preferences [Windows Forms], tracking
ms.assetid: 0dd8bca5-a6bf-4ac4-8eec-5725d08b38dc
ms.openlocfilehash: 49c7ceb431e9ab59b47e3b8b912e2881aeeef6c2
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583561"
---
# <a name="application-settings-overview"></a>Cenni preliminari sulle impostazioni delle applicazioni
Questo argomento descrive come creare e archiviare i dati delle impostazioni per conto dell'applicazione e degli utenti.  
  
 La funzionalità Impostazioni applicazione di Windows Form semplifica le operazioni di creazione, archiviazione e gestione delle preferenze personalizzate a livello di applicazione e utente nel computer client. Le impostazioni dell'applicazione Windows Form consentono non solo di archiviare dati applicativi quali stringhe di connessione a database, ma anche dati specifici dell'utente, quali preferenze per l'applicazione. L'uso di Visual Studio o di codice gestito personalizzato consente di creare nuove impostazioni, leggerle e scriverle su disco, associarle a proprietà di form e convalidare i dati delle impostazioni prima di caricarle e salvarle.  
  
 Le impostazioni dell'applicazione consente agli sviluppatori di salvare lo stato nella propria applicazione con un minimo di codice personalizzato e sostituendo le proprietà dinamiche nelle versioni precedenti di .NET Framework. Contengono molti miglioramenti rispetto alle proprietà dinamiche, che sono di sola lettura, ad associazione tardiva e richiedono ulteriore programmazione personalizzata. Le classi delle proprietà dinamiche sono state mantenute in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], ma sono solo classi shell che eseguono il wrapping delle classi delle impostazioni dell'applicazione.  
  
## <a name="what-are-application-settings"></a>Informazioni sulle impostazioni dell'applicazione.  
 Le applicazioni Windows Form richiedono spesso dati di importanza fondamentale per l'esecuzione che tuttavia non è opportuno includere direttamente nel codice dell'applicazione. Se l'applicazione usa un servizio Web o un server di database, è consigliabile archiviare le informazioni in un file separato, in modo che sia possibile modificarle in futuro senza dover ricompilare. Analogamente, è possibile che le applicazioni richiedano di archiviare dati specifici per l'utente corrente. Molte applicazioni, ad esempio, dispongono di preferenze utente che ne personalizzano l'aspetto e il comportamento.  
  
 Le impostazioni dell'applicazione soddisfano entrambe le necessità in quanto costituiscono un semplice metodo per l'archiviazione di impostazioni tanto a livello di applicazione quanto a livello di utente nel computer client. Usando Visual Studio o un editor di codice è possibile definire un'impostazione per una data proprietà specificandone il nome, il tipo di dati e l'ambito (applicazione o utente). È anche possibile inserire impostazioni correlate in gruppi denominati per semplificarne l'impiego e la leggibilità. Una volta definite, le impostazioni assumono carattere permanente e vengono lette automaticamente in memoria in fase di esecuzione. Un'architettura modulare rende possibile la modifica del meccanismo di persistenza, ma per impostazione predefinita viene usato il file system locale.  
  
 Impostazioni applicazione rende permanenti i dati in formato XML inserendoli in file di configurazione diversi (con estensione config) a seconda dell'ambito dell'impostazione (applicazione o utente). Nella maggior parte dei casi le impostazioni relative all'applicazione sono di sola lettura perché contengono informazioni sul programma e normalmente non è necessario sovrascriverle. Per contro, le impostazioni relative all'utente possono essere lette e scritte senza problemi in fase di esecuzione anche se l'applicazione è eseguita con attendibilità parziale. Per altre informazioni sull'attendibilità parziale, vedere [Security in Windows Forms Overview](../security-in-windows-forms-overview.md).  
  
 Le impostazioni vengono archiviate come frammenti XML nei file di configurazione. Le impostazioni con ambito di applicazione sono rappresentate dall'elemento `<application.Settings>` e di solito sono inserite in *app*.exe.config, dove *app* è il nome del file eseguibile principale. Le impostazioni con ambito di utente sono rappresentate dall'elemento `<userSettings>` e inserite in *utente*.config, dove *utente* è il nome dell'utente che esegue l'applicazione in quel momento. È necessario distribuire il file *app*.exe.config con l'applicazione. L'architettura delle impostazioni creerà i file *utente*.config su richiesta la prima volta che nell'applicazione verranno salvate le impostazioni per tale utente. È anche possibile definire un blocco `<userSettings>` in *app*.exe.config per fornire valori predefiniti per le impostazioni con ambito di utente.  
  
 Anche per i controlli personalizzati è possibile salvare le impostazioni implementando l'interfaccia <xref:System.Configuration.IPersistComponentSettings> , che espone il metodo <xref:System.Configuration.IPersistComponentSettings.SaveSettings%2A> . Il controllo <xref:System.Windows.Forms.ToolStrip> di Windows Form implementa questa interfaccia per salvare la posizione delle barre degli strumenti e dei relativi elementi tra le sessioni di un'applicazione. Per altre informazioni sui controlli personalizzati e le impostazioni dell'applicazione, vedere [Application Settings for Custom Controls](application-settings-for-custom-controls.md) (Impostazioni delle applicazioni per i controlli personalizzati).  
  
## <a name="limitations-of-application-settings"></a>Limitazioni della funzionalità Impostazioni applicazione  
 È possibile usare le impostazioni dell'applicazione in un'applicazione non gestita che ospita .NET Framework. Le impostazioni non funzioneranno correttamente in ambienti come i componenti aggiuntivi di Visual Studio, C++ per Microsoft Office, i controlli contenuti in Internet Explorer o i componenti aggiuntivi e i progetti di Microsoft Outlook.  
  
 Al momento non è possibile eseguire l'associazione ad alcune proprietà nei Windows Form. L'esempio più evidente è la proprietà <xref:System.Windows.Forms.Form.ClientSize%2A> , in quanto eseguendo l'associazione a questa proprietà si genera un comportamento non prevedibile in fase di esecuzione. In genere è possibile ovviare a questi problemi salvando e caricando le impostazioni a livello di codice.  
  
 Le impostazioni dell'applicazione non includono funzionalità incorporate per crittografare automaticamente le informazioni. Non archiviare mai informazioni correlate alla sicurezza, ad esempio password di database, in testo non crittografato. Se si vogliono archiviare informazioni riservate, lo sviluppatore dell'applicazione è responsabile di garantirne la sicurezza. Se si vogliono archiviare le stringhe di connessione, è consigliabile usare la sicurezza integrata di Windows e non ricorrere a password impostate come hardcoded nell'URL. Per altre informazioni, vedere [Code Access Security and ADO.NET](../../data/adonet/code-access-security.md).  
  
## <a name="getting-started-with-application-settings"></a>Guida introduttiva alle impostazioni dell'applicazione  
 Se si usa Visual Studio, per definire le impostazioni in Progettazione Windows Form usare la proprietà **(ApplicationSettings)** nella finestra **Proprietà** . Quando si definiscono le impostazioni in questo modo, viene creata automaticamente una classe wrapper gestita personalizzata che stabilisce un'associazione tra ogni impostazione e una proprietà di classe. Visual Studio stabilisce inoltre l'associazione tra l'impostazione e una proprietà su un form o controllo, in modo che le impostazioni del controllo vengano ripristinate automaticamente alla visualizzazione del form e salvate automaticamente alla chiusura.  
  
 Se si desidera un controllo maggiore sulle impostazioni, è possibile definire una classe wrapper personalizzata per le impostazioni dell'applicazione. Questa operazione viene eseguita derivando una classe da <xref:System.Configuration.ApplicationSettingsBase>, aggiungendo una proprietà corrispondente a ogni impostazione e applicando attributi speciali alle proprietà. Per informazioni sulla creazione di classi wrapper, vedere [Application Settings Architecture](application-settings-architecture.md) (Architettura Impostazioni applicazione).  
  
 È anche possibile usare la classe <xref:System.Windows.Forms.Binding> per associare le impostazioni alle proprietà a livello di codice su form e controlli.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- <xref:System.Configuration.IPersistComponentSettings>
- [Procedura: Convalidare le impostazioni applicazione](how-to-validate-application-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
- [Procedura: Leggere le impostazioni in fase di esecuzione conC#](how-to-read-settings-at-run-time-with-csharp.md)
- [Uso delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Application Settings Architecture](application-settings-architecture.md)
- [Application Settings for Custom Controls](application-settings-for-custom-controls.md)
