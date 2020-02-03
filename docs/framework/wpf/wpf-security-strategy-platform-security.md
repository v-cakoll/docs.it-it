---
title: Strategia di sicurezza della piattaforma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform security model [WPF]
- Common Language Runtime (CLR) security features
- operating system security model [WPF]
- Internet Explorer security features [WPF]
- Security-Critical method
- CLR security features [WPF]
- security model [WPF]
- security model [WPF], platform
- WPF [WPF], about security model
- Windows Presentation Foundation [WPF], about security model
- security model [WPF], operating system
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
ms.openlocfilehash: 1ef705fcf046af1f4136ddcf1b29f417c0d72c83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741859"
---
# <a name="wpf-security-strategy---platform-security"></a>Strategia di sicurezza di WPF - Sicurezza della piattaforma
Sebbene Windows Presentation Foundation (WPF) fornisca un'ampia gamma di servizi di sicurezza, sfrutta anche le funzionalità di sicurezza della piattaforma sottostante, che include il sistema operativo, CLR e Internet Explorer. Questi livelli combinano per fornire a WPF un modello di sicurezza sicuro e di difesa avanzato che tenta di evitare un singolo punto di errore, come illustrato nella figura seguente:  
  
 ![Diagramma che mostra il modello di sicurezza WPF.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 Nella parte restante di questo argomento vengono illustrate le funzionalità di ognuno di questi livelli che riguardano in modo specifico WPF.  

## <a name="operating-system-security"></a>Sicurezza del sistema operativo  
Il nucleo di Windows offre diverse funzionalità di sicurezza che costituiscono la base di sicurezza per tutte le applicazioni Windows, incluse quelle compilate con WPF. In questo argomento viene illustrata la vasta gamma di queste funzionalità di sicurezza importanti per WPF, nonché il modo in cui WPF si integra con loro per offrire un'ulteriore difesa in profondità.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Oltre a una revisione generale e al potenziamento di Windows, sono disponibili tre funzionalità chiave di [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] che verranno illustrate in questo argomento:  
  
- Compilazione /GS  
  
- Microsoft Windows Update.  
  
#### <a name="gs-compilation"></a>Compilazione /GS  
 [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] offre protezione ricompilando molte librerie di sistema principali, incluse tutte le dipendenze WPF, ad esempio CLR, per ridurre i sovraccarichi del buffer. A tale scopo, è necessario usare il parametro /GS con il compilatore da riga di comando di C/C++. Anche se i sovraccarichi del buffer dovrebbero essere evitati in modo esplicito, la compilazione /GS rappresenta un esempio di difesa da potenziali vulnerabilità create accidentalmente o intenzionalmente.  
  
 In passato i sovraccarichi del buffer sono stati causa di molte violazioni della sicurezza a impatto elevato. Si verifica un sovraccarico del buffer quando un utente malintenzionato sfrutta una vulnerabilità del codice per introdurre codice dannoso che viene scritto oltre i limiti di un buffer. Il malintenzionato sarà così in grado di assumere il controllo del processo in cui il codice è in esecuzione, sovrascrivendo l'indirizzo di ritorno di una funzione per indurre l'esecuzione del proprio codice dannoso. Il risultato sarà l'esecuzione di codice arbitrario attraverso codice dannoso con gli stessi privilegi del processo di cui è stato assunto il controllo.  
  
 A un livello elevato, il flag del compilatore-GS protegge da alcuni potenziali sovraccarichi del buffer inserendo uno speciale cookie di sicurezza per proteggere l'indirizzo di ritorno di una funzione con buffer di stringa locali. Dopo la restituzione di un risultato da parte di una funzione, il cookie di sicurezza viene confrontato con il suo valore precedente. Se il valore è cambiato, è possibile che si sia verificato un sovraccarico del buffer e che il processo venga interrotto con una condizione di errore. L'interruzione del processo impedisce l'esecuzione di codice potenzialmente dannoso. Per ulteriori informazioni, vedere [-GS (controllo di sicurezza del buffer)](/cpp/build/reference/gs-buffer-security-check) .  
  
 WPF viene compilato con il flag/GS per aggiungere un altro livello di difesa alle applicazioni WPF.  
  
### <a name="windows-vista"></a>Windows Vista  
Gli utenti WPF in Windows Vista trarranno vantaggio dai miglioramenti aggiuntivi della sicurezza del sistema operativo, inclusi l'accesso utente con privilegi minimi, i controlli di integrità del codice e l'isolamento dei privilegi.  
  
#### <a name="user-account-control-uac"></a>Controllo dell'account utente  
 Attualmente, gli utenti di Windows tendono a essere eseguiti con privilegi di amministratore perché molte applicazioni le richiedono per l'installazione o l'esecuzione o per entrambe. La scrittura delle impostazioni predefinite di un'applicazione nel Registro di sistema ne è un esempio.  
  
 Usare i privilegi di amministratore per eseguire un'applicazione significa che l'applicazione viene eseguita da processi a cui sono stati concessi i privilegi di amministratore. In termini di sicurezza, ciò significa che eventuale codice dannoso che assume il controllo di un processo eseguito con privilegi di amministratore erediterà automaticamente quei privilegi, incluso l'accesso a risorse di sistema critiche.  
  
 Un modo per proteggersi da una tale minaccia per la sicurezza consiste nell'eseguire le applicazioni con la quantità minima necessaria di privilegi. Questo è noto come principio dei privilegi minimi ed è una funzionalità di base del sistema operativo Windows. Questa funzionalità è denominata controllo dell'account utente (UAC) e viene utilizzata da Windows UAC in due modi principali:  
  
- Per eseguire la maggior parte delle applicazioni con privilegi UAC per impostazione predefinita, anche se l'utente è un amministratore. Solo le applicazioni che richiedono i privilegi di amministratore verranno eseguite con i privilegi di amministratore. Per essere eseguite con i privilegi di amministratore, le applicazioni devono essere contrassegnate in modo esplicito nel manifesto dell'applicazione o come voce nei criteri di sicurezza.  
  
- Per fornire soluzioni di compatibilità come la virtualizzazione. Molte applicazioni, ad esempio, provano a scrivere in percorsi limitati, come C:\Programmi. Per le applicazioni eseguite in ambito UAC, esiste un percorso alternativo specifico di ogni utente in cui è possibile scrivere senza disporre dei privilegi di amministratore. Per le applicazioni eseguite in ambito UAC, il percorso C:\Programmi viene virtualizzato affinché le applicazioni scrivano direttamente nel percorso alternativo specifico di ogni utente. Questa soluzione di compatibilità consente di eseguire molte applicazioni che in passato non sarebbe stato possibile eseguire in base al principio UAC.  
  
#### <a name="code-integrity-checks"></a>Controlli di integrità del codice  
 Windows Vista incorpora controlli di integrità del codice più approfonditi per impedire l'inserimento di codice dannoso nei file di sistema o nel kernel in fase di caricamento/esecuzione. Questo va oltre la protezione dei file di sistema.  
   
### <a name="limited-rights-process-for-browser-hosted-applications"></a>Processo con diritti limitati per le applicazioni ospitate nei browser  
 Le applicazioni WPF ospitate da browser vengono eseguite nella sandbox dell'area Internet. L'integrazione di WPF con Microsoft Internet Explorer estende questa protezione con supporto aggiuntivo.  
  
 Poiché le applicazioni browser XAML (XBAPs) vengono in genere create mediante sandbox dal set di autorizzazioni dell'area Internet, la rimozione di questi privilegi non danneggia le applicazioni browser XAML (XBAPs) dal punto di vista della compatibilità. Viene invece creato un livello di difesa aggiuntivo; se un'applicazione eseguita in una sandbox è in grado di sfruttare altri livelli e di assumere il controllo del processo, il processo disporrà comunque unicamente di privilegi limitati.  
  
 Vedere [uso di un account utente con privilegi minimi](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
## <a name="common-language-runtime-security"></a>Sicurezza di Common Language Runtime (CLR)  
 Il Common Language Runtime (CLR) offre una serie di vantaggi di sicurezza chiave che includono la convalida e la verifica, la sicurezza dall'accesso di codice e la metodologia critica per la sicurezza.  
    
### <a name="validation-and-verification"></a>Convalida e verifica  
 Per garantire l'integrità e l'isolamento degli assembly, CLR utilizza un processo di convalida. La convalida CLR garantisce che gli assembly siano isolati convalidando il formato di file eseguibile portabile (PE) per gli indirizzi che puntano all'esterno dell'assembly. La convalida CLR convalida inoltre l'integrità dei metadati incorporati all'interno di un assembly.  
  
 Per garantire l'indipendenza dai tipi, impedire problemi di sicurezza comuni, ad esempio sovraccarichi del buffer, e abilitare la sandboxing tramite l'isolamento dei processi secondari, la sicurezza CLR usa il concetto di verifica.  
  
 Le applicazioni gestite vengono compilate in Microsoft Intermediate Language (MSIL). Quando vengono eseguiti metodi in un'applicazione gestita, il relativo MSIL viene compilato in codice nativo tramite la compilazione JIT. La compilazione JIT include un processo di verifica riguardante molte regole di sicurezza e affidabilità per garantire che il codice:  
  
- non violi contratti di tipo  
  
- non causi sovraccarichi del buffer  
  
- non acceda alla memoria in modo irregolare o eccessivo.  
  
 Il codice gestito che non rispetta le regole di verifica non verrà eseguito, a meno che non venga considerato codice attendibile.  
  
 Il vantaggio del codice verificabile è il motivo principale per cui WPF si basa sul .NET Framework. Pertanto, più esteso sarà l'uso di codice verificabile, minori saranno le possibilità di sfruttare le vulnerabilità del sistema.  
  
### <a name="code-access-security"></a>Sicurezza dall'accesso di codice  
 Un computer client espone un'ampia varietà di risorse a cui un'applicazione gestita ha accesso, ad esempio il file system, il Registro di sistema, i servizi di stampa, l'interfaccia utente, la reflection e le variabili di ambiente. Prima che un'applicazione gestita possa accedere a una qualsiasi delle risorse in un computer client, deve disporre di .NET Framework autorizzazione. Un'autorizzazione in CAS è una sottoclasse del <xref:System.Security.CodeAccessPermission>; CAS implementa una sottoclasse per ogni risorsa a cui possono accedere le applicazioni gestite.  
  
 Il set di autorizzazioni che un'applicazione gestita viene concessa dalle CA quando viene avviata l'esecuzione è noto come set di autorizzazioni ed è determinato dall'evidenza fornita dall'applicazione. Per le applicazioni WPF, l'evidenza fornita è la posizione, o area, da cui vengono avviate le applicazioni. CA identifica le zone seguenti:  
  
- **Risorse del computer**. Applicazioni avviate dal computer client (completamente attendibili).  
  
- **Intranet locale**. Applicazioni avviate da Intranet (parzialmente attendibili).  
  
- **Internet**. Applicazioni avviate da Internet (meno attendibili).  
  
- **Siti attendibili**. Applicazioni identificate da un utente come attendibili (meno attendibili).  
  
- **Siti non attendibili**. Applicazioni identificate da un utente come non attendibili (non attendibili).  
  
 Per ognuna di queste zone, CAS fornisce un set di autorizzazioni predefinito che include le autorizzazioni che corrispondono al livello di attendibilità associato a ciascuna di esse. tra cui:  
  
- **FullTrust**. Per le applicazioni avviate dalla zona **computer locale** . Sono concesse tutte le autorizzazioni possibili.  
  
- **LocalIntranet**. Per le applicazioni avviate dall'area **Intranet locale** . Viene concesso un sottoinsieme di autorizzazioni per fornire un accesso moderato alle risorse di un computer client, tra cui spazio di memorizzazione isolato, accesso dell'interfaccia utente senza restrizioni, finestre di dialogo di file senza restrizioni, reflection limitata, accesso limitato alle variabili di ambiente. Le autorizzazioni per risorse critiche come il Registro di sistema non vengono concesse.  
  
- **Internet**. Per le applicazioni avviate dall'area **Internet** o **siti attendibili** . Viene concesso un sottoinsieme di autorizzazioni per fornire accesso limitato alle risorse di un computer client, tra cui spazio di memorizzazione isolato, solo apertura di file e interfaccia utente limitata. In pratica, questo set di autorizzazioni isola le applicazioni dal computer client.  
  
 Alle applicazioni identificate come provenienti dall'area **siti non attendibili** non vengono concesse le autorizzazioni per le autorità di certificazione. Di conseguenza, queste non dispongono di alcun set di autorizzazioni predefinito.  
  
 Nella figura seguente viene illustrata la relazione tra aree, set di autorizzazioni, autorizzazioni e risorse:  
  
 ![Diagramma che mostra i set di autorizzazioni CAS.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Le restrizioni della sandbox di sicurezza dell'area Internet si applicano ugualmente a qualsiasi codice che un'applicazione XBAP importa da una libreria di sistema, incluso WPF. In questo modo si garantisce che ogni bit del codice venga bloccato, anche WPF. Sfortunatamente, per poter eseguire, un'applicazione XBAP deve eseguire funzionalità che richiedono più autorizzazioni rispetto a quelle abilitate dalla sandbox di sicurezza dell'area Internet.  
  
 Si consideri un'applicazione XBAP che include la pagina seguente:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Per eseguire questa applicazione XBAP, il codice WPF sottostante deve eseguire più funzionalità di quelle disponibili per l'applicazione XBAP chiamante, tra cui:  
  
- Creazione di un handle di finestra (HWND) per il rendering  
  
- Invio di messaggi  
  
- Caricamento del tipo di carattere Tahoma  
  
 Da un punto di vista della sicurezza, consentire l'accesso diretto a queste operazioni dall'applicazione eseguita in una sandbox avrebbe conseguenze devastanti.  
  
 Fortunatamente, WPF soddisfa questa situazione consentendo l'esecuzione di queste operazioni con privilegi elevati per conto dell'applicazione creata mediante sandbox. Mentre tutte le operazioni WPF vengono verificate in base alle autorizzazioni di sicurezza limitate dell'area Internet del dominio dell'applicazione XBAP, a WPF, come ad altre librerie di sistema, viene concesso un set di autorizzazioni che include tutte le autorizzazioni possibili.
  
 A tale scopo è necessario che WPF riceva privilegi elevati evitando che tali privilegi vengano regolati dal set di autorizzazioni dell'area Internet del dominio dell'applicazione host.  
  
 A tale scopo, WPF usa il metodo **Assert** di un'autorizzazione. Nel codice riportato di seguito viene illustrata questa operazione.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 L' **asserzione** impedisce essenzialmente le autorizzazioni illimitate richieste da WPF di essere limitate dalle autorizzazioni dell'area Internet dell'applicazione XBAP.  
  
 Dal punto di vista della piattaforma, WPF è responsabile dell'uso corretto di **Assert** . un uso errato di **Assert** potrebbe consentire a codice dannoso di elevare i privilegi. Di conseguenza, è importante chiamare solo **Assert** quando necessario e assicurarsi che le restrizioni della sandbox rimangano intatte. Ad esempio, al codice sandbox non è consentita l'apertura di file casuali, ma è consentito l'uso dei tipi di carattere. WPF consente alle applicazioni sandbox di usare la funzionalità dei tipi di carattere chiamando **Assert**e per consentire a WPF di leggere i file che contengono tali caratteri per conto dell'applicazione creata mediante sandbox.  
  
### <a name="clickonce-deployment"></a>Distribuzione ClickOnce  
 ClickOnce è una tecnologia di distribuzione completa inclusa con .NET Framework e si integra con Visual Studio. per informazioni dettagliate, vedere la pagina relativa alla [sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) . Le applicazioni WPF autonome possono essere distribuite tramite ClickOnce, mentre le applicazioni ospitate da browser devono essere distribuite con ClickOnce.  
  
 Alle applicazioni distribuite con ClickOnce viene assegnato un livello di sicurezza aggiuntivo rispetto alla sicurezza dall'accesso di codice (CAS); sostanzialmente, le applicazioni distribuite ClickOnce richiedono le autorizzazioni necessarie. A tali applicazioni vengono concesse solo quelle autorizzazioni se non superano l'insieme di autorizzazioni dell'area da cui vengono distribuite. Riducendo il set di autorizzazioni solo a quelle necessarie, anche se inferiori a quelle fornite dal set di autorizzazioni dell'area di avvio, il numero di risorse a cui l'applicazione ha accesso viene ridotto al minimo. Di conseguenza, se si perde il controllo dell'applicazione, le vulnerabilità del computer client saranno ridotte.  
  
### <a name="security-critical-methodology"></a>Metodologia critica per la sicurezza  
 Il codice WPF che usa le autorizzazioni per abilitare la sandbox dell'area Internet per le applicazioni XBAP deve essere mantenuto al massimo livello possibile di controllo e controllo di sicurezza. Per semplificare questo requisito, .NET Framework fornisce un nuovo supporto per la gestione del codice che eleva i privilegi. In particolare, CLR consente di identificare il codice che eleva i privilegi e di contrassegnarlo con l'<xref:System.Security.SecurityCriticalAttribute>; qualsiasi codice non contrassegnato con <xref:System.Security.SecurityCriticalAttribute> diventa *trasparente* utilizzando questa metodologia. Viceversa, il codice gestito non contrassegnato con <xref:System.Security.SecurityCriticalAttribute> non può elevare i privilegi.  
  
 La metodologia critica per la sicurezza consente all'organizzazione del codice WPF che eleva i privilegi nel *kernel critico*per la sicurezza, mentre il resto diventa trasparente. L'isolamento del codice critico per la sicurezza consente al team di progettazione WPF di concentrare un'analisi di sicurezza e un controllo del codice sorgente aggiuntivi sul kernel critico per la sicurezza, oltre alle procedure di sicurezza standard (vedere [strategia di sicurezza WPF-Progettazione della sicurezza](wpf-security-strategy-security-engineering.md)).  
  
 Si noti che .NET Framework consente a codice attendibile di estendere la sandbox dell'area Internet XBAP consentendo agli sviluppatori di scrivere assembly gestiti contrassegnati con <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) e distribuiti nella global assembly cache (GAC) dell'utente. Contrassegnare un assembly con APTCA è un'operazione estremamente delicata dal punto di vista della sicurezza in quanto consente a qualsiasi codice di chiamare quell'assembly, incluso eventuale codice dannoso proveniente da Internet. È necessario esercitare massima cautela, seguire le procedure consigliate e gli utenti devono scegliere di considerare attendibile un programma software per poterlo installare.  
  
## <a name="microsoft-internet-explorer-security"></a>Sicurezza di Microsoft Internet Explorer  
 Oltre a ridurre i problemi di sicurezza e a semplificare la configurazione della sicurezza, Microsoft Internet Explorer 6 (SP2) contiene diverse funzionalità che migliorano la sicurezza per gli utenti delle applicazioni browser XAML (XBAP). Tramite queste funzionalità si tenta di fornire agli utenti un maggiore controllo sulla loro esperienza di esplorazione.  
  
 Prima di IE6 SP2, gli utenti potevano essere soggetti a uno dei seguenti elementi:  
  
- Finestre popup casuali.  
  
- Reindirizzamento di script non chiaro.  
  
- Numerose finestre di dialogo di sicurezza in alcuni siti Web.  
  
 In alcuni casi, i siti Web non affidabili tentano di ingannare gli utenti effettuando lo spoofing dell'installazione [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] o visualizzando ripetutamente una finestra di dialogo di installazione di Microsoft ActiveX, anche se è possibile che l'utente lo abbia annullato. Tramite queste tecniche, è possibile che un numero significativo di utenti sia stato indotto a prendere decisioni che hanno causato l'installazione di applicazioni spyware.  
  
 IE6 SP2 include diverse funzionalità per attenuare questi tipi di problemi, che ruotano attorno al concetto di avvio dell'utente. IE6 SP2 rileva quando un utente ha fatto clic su un collegamento o un elemento della pagina prima di un'azione, nota come *avvio da parte dell'utente*, e lo considera in modo diverso rispetto a quando un'azione simile viene invece attivata dallo script in una pagina. Ad esempio, IE6 SP2 incorpora un **blocco popup** che rileva quando un utente fa clic su un pulsante prima che la pagina crei un popup. In questo modo IE6 SP2 è in grado di consentire i popup più innocui, evitando i popup che non vengono richiesti né desiderati dagli utenti. I popup bloccati vengono intercettati sotto la nuova **barra informazioni**, che consente all'utente di eseguire manualmente l'override del blocco e di visualizzare il popup.  
  
 Viene anche applicata la stessa logica di avvio utente per **aprire**/**salvare** i prompt di sicurezza. Le finestre di dialogo di installazione ActiveX vengono sempre intercettate sotto la barra informazioni a meno che non rappresentino un aggiornamento da un controllo installato in precedenza. Queste misure consentono agli utenti un'esperienza più controllata e sicura, perché sono protetti da quei siti che con l'inganno inducono a installare software indesiderato o dannoso.  
  
 Queste funzionalità proteggono inoltre i clienti che utilizzano IE6 SP2 per accedere ai siti Web che consentono loro di scaricare e installare le applicazioni WPF. In particolare, questo è dovuto al fatto che IE6 SP2 offre un'esperienza utente migliore che riduce la possibilità per gli utenti di installare applicazioni dannose o malintenzionate indipendentemente dalla tecnologia usata per compilarlo, incluso WPF. WPF aggiunge queste protezioni usando ClickOnce per facilitare il download delle applicazioni tramite Internet. Poiché le applicazioni browser XAML (XBAP) vengono eseguite in una sandbox di sicurezza dell'area Internet, possono essere avviate facilmente. D'altra parte, le applicazioni WPF autonome richiedono l'attendibilità totale per l'esecuzione. Per queste applicazioni, ClickOnce visualizzerà una finestra di dialogo di sicurezza durante il processo di avvio per notificare l'uso dei requisiti di sicurezza aggiuntivi dell'applicazione. Questa operazione, che deve essere avviata dall'utente, verrà determinata dalla logica avviata dall'utente e potrà essere annullata.  
  
 Internet Explorer 7 incorpora ed estende le funzionalità di sicurezza di IE6 SP2 come parte di un costante impegno per la sicurezza.  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza dall'accesso di codice](../misc/code-access-security.md)
- [Sicurezza](security-wpf.md)
- [Sicurezza con attendibilità parziale in WPF](wpf-partial-trust-security.md)
- [Strategia di sicurezza WPF - Progettazione della sicurezza](wpf-security-strategy-security-engineering.md)
