---
title: Considerazioni aggiuntive sulla sicurezza in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: 276def9db2ff610a22b42a88ad658727793b53de
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718909"
---
# <a name="additional-security-considerations-in-windows-forms"></a>Considerazioni aggiuntive sulla sicurezza in Windows Form
Le impostazioni di sicurezza di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] potrebbero modificare l'esecuzione di un'applicazione in un ambiente ad attendibilità parziale rispetto al computer locale. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] limita l'accesso a tali risorse locali critiche, ad esempio il file system, la rete e le API non gestite. Le impostazioni di sicurezza influiscono sulla capacità di chiamare l'API Microsoft Win32 o altre API non verificabili dal sistema di sicurezza. La sicurezza influisce inoltre su altri aspetti dell'applicazione, inclusi l'accesso ai file e ai dati e la stampa. Per altre informazioni sull'accesso a file e dati in un ambiente ad attendibilità parziale, vedere [More Secure File and Data Access in Windows Forms](more-secure-file-and-data-access-in-windows-forms.md) (Accesso più sicuro a file e dati in Windows Form). Per altre informazioni sulla stampa in un ambiente ad attendibilità parziale, vedere [More Secure Printing in Windows Forms](more-secure-printing-in-windows-forms.md) (Stampa più sicura in Windows Form).  
  
 Le sezioni seguenti illustrano come usare gli Appunti, modificare le finestre e chiamare l'API Win32 dalle applicazioni in esecuzione in un ambiente ad attendibilità parziale.  
  
## <a name="clipboard-access"></a>Accesso agli Appunti  
 Il <xref:System.Security.Permissions.UIPermission> classe Controlla accesso agli Appunti e associato <xref:System.Security.Permissions.UIPermissionClipboard> valore di enumerazione indica il livello di accesso. Nella tabella seguente sono elencati i livelli di autorizzazione possibili.  
  
|Valore UIPermissionClipboard|Descrizione|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|È possibile usare gli Appunti senza restrizioni.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|È possibile usare gli Appunti con alcune restrizioni. Possibilità di inserire dati negli Appunti (operazioni dei comandi Copia o Taglia) senza restrizioni. I controlli intrinseci che accettano operazioni Incolla, ad esempio una casella di testo, possono accettare i dati negli Appunti, ma i controlli utente non possono leggere a livello di codice dagli Appunti.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|Impossibile usare gli Appunti.|  
  
 Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> l'accesso e l'area Internet riceve <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> accesso. Ciò significa che l'applicazione può copiare dati negli Appunti, ma non può incollare negli Appunti o leggere dagli Appunti a livello di codice. Queste restrizioni impediscono ai programmi senza attendibilità totale di leggere il contenuto copiati negli Appunti da un'altra applicazione. Se l'applicazione richiede l'accesso completo agli Appunti ma non disporre delle autorizzazioni, sarà necessario elevarne le autorizzazioni. Per altre informazioni sull'elevazione delle autorizzazioni, vedere [General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)) (Amministrazione generale dei criteri di sicurezza).  
  
## <a name="window-manipulation"></a>Modifica delle finestre  
 Il <xref:System.Security.Permissions.UIPermission> classe controlla anche le autorizzazioni per eseguire la modifica delle finestre e altre azioni legate all'interfaccia utente e associato <xref:System.Security.Permissions.UIPermissionWindow> valore di enumerazione indica il livello di accesso. Nella tabella seguente sono elencati i livelli di autorizzazione possibili.  
  
 Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> l'accesso e l'area Internet riceve <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> accesso. Ciò significa che, nell'area Internet, l'applicazione può eseguire la maggior parte delle azioni legate a finestre e interfaccia utente, con conseguente modifica dell'aspetto della finestra. La finestra modificata visualizza una notifica alla prima esecuzione, contiene testo modificato nella barra del titolo e richiede un pulsante di chiusura nella medesima barra. La notifica e la barra del titolo indicano all'utente dell'applicazione che quest'ultima è in esecuzione ad attendibilità parziale.  
  
|Valore UIPermissionWindow|Descrizione|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Gli utenti possono usare tutte le finestre e tutti gli eventi input utente senza restrizioni.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Gli utenti possono usare solo le più sicure finestre principali e secondarie per il disegno e possono usare solo gli eventi input utente dell'interfaccia all'interno di tali finestre. Queste finestre sicure sono contrassegnate in modo chiaro e dispongono di restrizioni per la dimensione minima e massima. Le restrizioni impediscono attacchi di spoofing potenzialmente dannosi, ad esempio l'imitazione delle schermate di accesso o il desktop e limita l'accesso a livello di codice padre windows API correlate a messa a fuoco e sfrutta la <xref:System.Windows.Forms.ToolTip> (controllo),|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Gli utenti possono usare solo le più sicure finestre secondarie per il disegno e possono usare solo gli eventi input utente dell'interfaccia all'interno di tali finestre. Un controllo visualizzato all'interno di un browser è un esempio di finestra secondaria sicura.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Gli utenti non possono usare finestre o eventi dell'interfaccia utente. Non è possibile usare l'interfaccia utente.|  
  
 Ogni livello di autorizzazione identificato dal <xref:System.Security.Permissions.UIPermissionWindow> consente l'enumerazione meno azioni rispetto al livello superiore. Nelle tabelle seguenti vengono indicate le azioni che sono limitate dai <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> e <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valori. Per le autorizzazioni esattamente necessarie per ogni membro, vedere il riferimento per tale membro nella documentazione della libreria di classi .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> autorizzazione limita le azioni elencate nella tabella seguente.  
  
|Componente|Azioni limitate|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|-   Impostazione della proprietà <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-Recupero di <xref:System.Windows.Forms.Control.Parent%2A> proprietà.<br />-   Impostazione della proprietà `Region`.<br />-Chiamata di <xref:System.Windows.Forms.Control.FindForm%2A> , <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> e <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>, o <xref:System.Windows.Forms.Control.SetTopLevel%2A> (metodo).<br />-Chiamata di <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> metodo se il controllo restituito non è un figlio del controllo chiama.<br />-   Modifica del focus del controllo all'interno di un controllo contenitore.|  
|<xref:System.Windows.Forms.Cursor>|-   Impostazione della proprietà <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-Chiamata di <xref:System.Windows.Forms.Control.Hide%2A> (metodo).|  
|<xref:System.Windows.Forms.DataGrid>|-Chiamata di <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> (metodo).|  
|<xref:System.Windows.Forms.Form>|-Recupero il <xref:System.Windows.Forms.Form.ActiveForm%2A> o <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà.<br />-Impostazione di <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>, o <xref:System.Windows.Forms.Form.TopMost%2A> proprietà.<br />-Impostazione di <xref:System.Windows.Forms.Form.Opacity%2A> proprietà inferiore al 50%.<br />-Impostazione di <xref:System.Windows.Forms.Form.WindowState%2A> proprietà <xref:System.Windows.Forms.FormWindowState.Minimized> a livello di codice.<br />-Chiamata di <xref:System.Windows.Forms.Form.Activate%2A> (metodo).<br />-Uso di <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>, e <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow> <xref:System.Windows.Forms.FormBorderStyle> valori di enumerazione.|  
|<xref:System.Windows.Forms.NotifyIcon>|-Uso di <xref:System.Windows.Forms.NotifyIcon> componente è totalmente limitato.|  
  
 Il <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valore limita le azioni elencate nella tabella seguente, anche per le restrizioni applicate per il <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> valore.  
  
|Componente|Azioni limitate|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Visualizzazione di una finestra di dialogo derivata dal <xref:System.Windows.Forms.CommonDialog> classe.|  
|<xref:System.Windows.Forms.Control>|-Chiamata di <xref:System.Windows.Forms.Control.CreateGraphics%2A> (metodo).<br />-   Impostazione della proprietà <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Impostazione della proprietà <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-Chiamata di <xref:System.Windows.Forms.Form.Show%2A> (metodo).|  
  
### <a name="hosting-third-party-controls"></a>Hosting di controlli di terze parti  
 Se i moduli ospitano controlli di terze parti, può verificarsi un altro tipo di modifica delle finestre. Un controllo di terze parti è qualsiasi custom <xref:System.Windows.Forms.UserControl> di non aver sviluppato e compilato dall'utente. Sebbene lo scenario di hosting sia difficile da sfruttare, un controllo di terze parti può almeno in teoria espandere la propria superficie di rendering per coprire l'intera area del modulo. Il controllo potrebbe quindi imitare una finestra di dialogo critica e richiedere informazioni come combinazioni di nome utente e password o numeri di conti corrente degli utenti.  
  
 Per limitare questo rischio, usare solo controlli di terze parti considerati attendibili. Se si usano controlli di terze parti scaricati da origini non verificabili, si consiglia di esaminarne il codice sorgente alla ricerca di exploit potenziali. Dopo aver verificato che l'origine non è dannosa, compilare l'assembly da sé per assicurarsi che l'origine corrisponda.  
  
## <a name="win32-api-calls"></a>Chiamate API Win32  
 Se la progettazione dell'applicazione richiede la chiamata a una funzione dell'API Win32, si accederà a codice non gestito. In questo caso, lavorando con le chiamate o i valori dell'API Win32, non è possibile determinare le azioni del codice relativamente alla finestra o al sistema operativo. Il <xref:System.Security.Permissions.SecurityPermission> classe e il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> pari al <xref:System.Security.Permissions.SecurityPermissionFlag> controlla l'accesso al codice non gestito. Un'applicazione può accedere a codice non gestito solo quando viene concesso il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> l'autorizzazione. Per impostazione predefinita, solo le applicazioni in esecuzione in locale possono chiamare codice non gestito.  
  
 Alcuni membri di Windows Form offrono accesso non gestito che richiede il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> l'autorizzazione. Nella tabella seguente elenca i membri di <xref:System.Windows.Forms> dello spazio dei nomi che richiedono l'autorizzazione. Per altre informazioni sulle autorizzazioni necessarie per un membro, vedere la documentazione della libreria di classi .NET Framework.  
  
|Componente|Member|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|-    Metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> Proprietà<br />-    Metodo `Exit`<br />-    Metodo <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   <xref:System.Windows.Forms.Application.ThreadException> Evento|  
|<xref:System.Windows.Forms.CommonDialog>|-    Metodo <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ (metodo)<br />-    Metodo <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />-    Metodo <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|-    Metodo <xref:System.Windows.Forms.Control.CreateParams%2A><br />-    Metodo <xref:System.Windows.Forms.Control.DefWndProc%2A><br />-    Metodo <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />-    Metodo <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> Metodi<br />-    Metodo <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> Classe|  
|<xref:System.Windows.Forms.Screen>|-    Metodo <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|-    Metodo <xref:System.Windows.Forms.SendKeys.Send%2A><br />-    Metodo <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Se l'applicazione non è autorizzato a chiamare codice non gestito, l'applicazione deve richiedere <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione oppure è necessario prendere in considerazione modi alternativi di implementazione di funzionalità, in molti casi, Windows Form fornisce un'alternativa gestita alle API Win32 funzioni. Se non esistono metodi alternativi e l'applicazione deve accedere a codice non gestito, sarà necessario elevare le autorizzazioni per l'applicazione.  
  
 L'autorizzazione a chiamare codice non gestito consente a un'applicazione di eseguire praticamente qualsiasi operazione. Fornire pertanto tale autorizzazione solo alle applicazioni provenienti da fonti attendibili. In alternativa, a seconda dell'applicazione, la caratteristica che esegue la chiamata al codice non gestite potrebbe essere facoltativa oppure abilitata solo in un ambiente ad attendibilità totale. Per altre informazioni sulle autorizzazioni pericolose, vedere [Autorizzazioni pericolose e amministrazione dei criteri](../misc/dangerous-permissions-and-policy-administration.md). Per altre informazioni sull'elevazione delle autorizzazioni, vedere [General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)) (Amministrazione generale dei criteri di sicurezza).  
  
## <a name="see-also"></a>Vedere anche
- [Accesso più sicuro a file e dati in Windows Form](more-secure-file-and-data-access-in-windows-forms.md)
- [Stampa più sicura in Windows Forms](more-secure-printing-in-windows-forms.md)
- [Panoramica della sicurezza in Windows Forms](security-in-windows-forms-overview.md)
- [Sicurezza di Windows Form](windows-forms-security.md)
- [Sicurezza di applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications)
