---
title: Rendering dei controlli con stili visivi
ms.date: 03/30/2017
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- themes [Windows Forms], XP visual styles in Window Forms
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- visual themes [Windows Forms], rendering Windows Forms controls
- user controls [Windows Forms], painting
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a5b178ba-610e-46c4-a6c0-509c0886a744
ms.openlocfilehash: a7f2d810567d37021d5d4473204d9950d6834b9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="rendering-controls-with-visual-styles"></a>Rendering dei controlli con stili visivi
[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] offre supporto per il rendering dei controlli e di altri elementi dell'interfaccia utente (UI) di Windows usando gli stili di visualizzazione nei sistemi operativi che li supportano. Questo argomento illustra i diversi livelli di supporto di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per il rendering dei controlli e di altri elementi dell'interfaccia utente con lo stile di visualizzazione corrente del sistema operativo.  
  
## <a name="rendering-classes-for-common-controls"></a>Classi di rendering per i controlli comuni  
 Il rendering di un controllo si riferisce alla grafica dell'interfaccia utente di un controllo. Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> include la classe <xref:System.Windows.Forms.ControlPaint> per il rendering di alcuni controlli comuni di Windows Form. Questa classe consente tuttavia di disegnare controlli nello stile classico di Windows, pertanto può essere difficile mantenere un'esperienza coerente per l'interfaccia utente quando si creano controlli personalizzati nelle applicazioni in cui sono abilitati gli stili di visualizzazione.  
  
 Il [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] include le classi di <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi che eseguono il rendering di parti e stati dei controlli comuni con gli stili di visualizzazione. Ciascuna di queste classi include metodi `static` per la creazione del controllo o delle relative parti in un determinato stato con lo stile di visualizzazione corrente del sistema operativo.  
  
 Alcune di queste classi sono progettate per creare il relativo controllo, indipendentemente dalla disponibilità degli stili di visualizzazione. Se gli stili di visualizzazione sono abilitati, i membri della classe creeranno il relativo controllo con gli stili impostati. Se invece sono disabilitati, i membri della classe creeranno il controllo nello stile classico di Windows. Tali classi includono:  
  
-   <xref:System.Windows.Forms.ButtonRenderer>  
  
-   <xref:System.Windows.Forms.CheckBoxRenderer>  
  
-   <xref:System.Windows.Forms.GroupBoxRenderer>  
  
-   <xref:System.Windows.Forms.RadioButtonRenderer>  
  
 Altre classi possono creare il relativo controllo solo quando sono disponibili gli stili di visualizzazione e i membri di tali classi genereranno un'eccezione se gli stili di visualizzazione sono disabilitati. Tali classi includono:  
  
-   <xref:System.Windows.Forms.ComboBoxRenderer>  
  
-   <xref:System.Windows.Forms.ProgressBarRenderer>  
  
-   <xref:System.Windows.Forms.ScrollBarRenderer>  
  
-   <xref:System.Windows.Forms.TabRenderer>  
  
-   <xref:System.Windows.Forms.TextBoxRenderer>  
  
-   <xref:System.Windows.Forms.TrackBarRenderer>  
  
 Per altre informazioni sull'uso di queste classi per la creazione di un controllo, vedere [How to: Use a Control Rendering Class](../../../../docs/framework/winforms/controls/how-to-use-a-control-rendering-class.md).  
  
## <a name="visual-style-element-and-rendering-classes"></a>Elemento dello stile di visualizzazione e classi di rendering  
 Lo spazio dei nomi <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> include classi che consentono di disegnare e ottenere informazioni su qualsiasi controllo o elemento dell'interfaccia utente supportato dagli stili di visualizzazione. I controlli supportati includono i controlli comuni che hanno una classe di rendering nello spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> (vedere la sezione precedente), nonché altri controlli, ad esempio controlli Struttura a schede e controlli Rebar. Tra gli altri elementi dell'interfaccia utente supportati figurano le parti del menu **Start** , la barra delle applicazioni e l'area non client di Windows.  
  
 Le classi principali dello spazio dei nomi <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> sono <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> e <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>. <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> è una classe di base per l'identificazione di qualsiasi controllo o elemento dell'interfaccia utente supportato dagli stili di visualizzazione. Oltre a <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, lo spazio dei nomi <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> include molte classi nidificate di <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> con proprietà `static` che restituiscono un elemento <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> per ogni stato di un controllo, di una parte di controllo o di un altro elemento dell'interfaccia utente supportato dagli stili di visualizzazione.  
  
 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> offre i metodi per disegnare e ottenere informazioni su ogni elemento <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> definito dallo stile di visualizzazione corrente del sistema operativo. Le informazioni che possono essere recuperate su un elemento includono la dimensione predefinita, il tipo di sfondo e le definizioni dei colori. <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> esegue il wrapping della funzionalità dell'API degli stili di visualizzazione (UxTheme) dalla parte della shell di Windows di Windows Platform SDK. Per ulteriori informazioni, vedere [utilizzando gli stili di visualizzazione di Windows XP](https://msdn.microsoft.com/library/ms997649.aspx).  
  
 Per altre informazioni sull'uso di <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> e <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, vedere [How to: Render a Visual Style Element](../../../../docs/framework/winforms/controls/how-to-render-a-visual-style-element.md).  
  
## <a name="enabling-visual-styles"></a>Abilitazione degli stili di visualizzazione  
 Per abilitare gli stili di visualizzazione per un'applicazione scritta per [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0, i programmatori devono includere un manifesto dell'applicazione in cui si specifica che per disegnare i controlli verrà usata ComCtl32.dll versione 6 o successiva. Le applicazioni compilate con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.1 o successiva possono usare il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> della classe <xref:System.Windows.Forms.Application>.  
  
## <a name="checking-for-visual-styles-support"></a>Verifica del supporto degli stili di visualizzazione  
 La proprietà <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> della classe <xref:System.Windows.Forms.Application> indica se l'applicazione corrente sta creando i controlli con gli stili di visualizzazione. Quando si disegna un controllo personalizzato, è possibile controllare il valore di <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> per determinare se è necessario eseguire il rendering del controllo con o senza gli stili di visualizzazione. La tabella seguente elenca le quattro condizioni necessarie affinché <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> restituisca `true`.  
  
|Condizione|Note|  
|---------------|-----------|  
|Il sistema operativo supporta gli stili di visualizzazione.|Per verificare questa condizione separatamente, usare la proprietà <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsSupportedByOS%2A> della classe <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> .|  
|L'utente ha abilitato gli stili di visualizzazione nel sistema operativo.|Per verificare questa condizione separatamente, usare la proprietà <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsEnabledByUser%2A> della classe <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> .|  
|Gli stili di visualizzazione sono abilitati nell'applicazione.|Per abilitare gli stili di visualizzazione per un'applicazione, chiamare il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> o usare un manifesto dell'applicazione in cui si specifica che per disegnare i controlli verrà usata ComCtl32.dll versione 6 o successiva.|  
|Gli stili di visualizzazione vengono usati per disegnare l'area client delle finestre dell'applicazione.|Per verificare questa condizione separatamente, usare la proprietà <xref:System.Windows.Forms.Application.VisualStyleState%2A> della classe <xref:System.Windows.Forms.Application> e verificare che abbia il valore <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAreaEnabled?displayProperty=nameWithType> o <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAndNonClientAreasEnabled?displayProperty=nameWithType>.|  
  
 Per determinare quando un utente abilita o disabilita gli stili di visualizzazione o passa da uno stile di visualizzazione a un altro, verificare la presenza del valore <xref:Microsoft.Win32.UserPreferenceCategory.VisualStyle?displayProperty=nameWithType> nei gestori per gli eventi <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging?displayProperty=nameWithType> o <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Se si vuole usare <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> per il rendering di un controllo o di un elemento dell'interfaccia utente quando l'utente abilita o cambia gli stili di visualizzazione, assicurarsi di eseguire l'operazione durante la gestione dell'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> anziché dell'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging> . Se si usa la classe <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> durante la gestione di <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging>, verrà generata un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 [Disegno e rendering di controlli personalizzati](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)
