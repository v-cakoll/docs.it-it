---
title: Automazione interfaccia utente e ridimensionamento dello schermo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: 2a68a74fa6aadcaba21f142d394a1f8a3d8af371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179973"
---
# <a name="ui-automation-and-screen-scaling"></a>Automazione interfaccia utente e ridimensionamento dello schermo
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
A partire da Windows Vista, Windows consente agli utenti di modificare l'impostazione di punti per pollice (dpi) in modo che la maggior parte degli elementi dell'interfaccia utente sullo schermo appaia più grande. Anche se questa funzionalità è stata a lungo disponibile in Windows, nelle versioni precedenti il ridimensionamento doveva essere implementato dalle applicazioni. A partire da Windows Vista, Gestione finestre desktop esegue il ridimensionamento predefinito per tutte le applicazioni che non gestiscono il proprio ridimensionamento. Per le applicazioni client di automazione interfaccia utente è necessario tenere conto di questa funzionalità.  
  
<a name="Scaling_in_Windows_Vista"></a>
## <a name="scaling-in-windows-vista"></a>Ridimensionamento in Windows Vista  
 L'impostazione dpi predefinita è 96, il che significa che 96 pixel occupano una larghezza o un'altezza di un pollice nozionale. La misura esatta di un pollice dipende dalle dimensioni e dalla risoluzione fisica del monitor. Ad esempio, su un monitor con una larghezza di 12 pollici e una risoluzione orizzontale di 1280 pixel, una riga orizzontale di 96 pixel si estende per circa 9/10 di un pollice.  
  
 La modifica dell'impostazione dpi non equivale a modificare la risoluzione dello schermo. Con il ridimensionamento dpi, il numero di pixel fisici sullo schermo rimane invariato. Il ridimensionamento viene tuttavia applicato alle dimensioni e alla posizione degli elementi dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . È possibile eseguire il ridimensionamento automaticamente con Gestione finestre desktop per il desktop e per le applicazioni che non richiedono tale funzionalità in modo esplicito.  
  
 In effetti, quando l'utente imposta il fattore di scala su 120 dpi, un pollice verticale o orizzontale sullo schermo diventa più grande del 25%. Tutte le dimensioni vengono ridimensionate di conseguenza. L'offset di una finestra dell'applicazione dai bordi superiore e sinistro dello schermo aumenta del 25%. Se il ridimensionamento dell'applicazione è abilitato e l'applicazione non è compatibile con dpi, le [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] dimensioni della finestra aumentano nella stessa proporzione, insieme agli offset e alle dimensioni di tutti gli elementi in essa contenuti.  
  
> [!NOTE]
> Per impostazione predefinita, il dWM non esegue il ridimensionamento per le applicazioni non in grado di riconoscere dpi quando l'utente imposta il dpi su 120, ma lo esegue quando il dpi è impostato su un valore personalizzato di 144 o superiore. È tuttavia possibile ignorare questo comportamento predefinito.  
  
 Il ridimensionamento dello schermo crea nuove sfide per le applicazioni che dipendono dalle coordinate dello schermo. Lo schermo contiene ora due sistemi di coordinate: fisico e logico. Le coordinate fisiche di un punto sono l'offset effettivo in pixel dalla parte superiore sinistra dell'origine. Le coordinate logiche sono gli offset così come si presenterebbero se i pixel fossero ridimensionati.  
  
 Si supponga di progettare una finestra di dialogo con un pulsante in corrispondenza delle coordinate (100, 48). Quando questa finestra di dialogo viene visualizzata in corrispondenza dei 96 dpi predefiniti, il pulsante si trova in corrispondenza delle coordinate fisiche di (100, 48). A 120 dpi, si trova alle coordinate fisiche di (125, 60). Ma le coordinate logiche sono le stesse in qualsiasi impostazione dpi: (100, 48).  
  
 Le coordinate logiche sono importanti, perché rendono coerente il comportamento del sistema operativo e delle applicazioni indipendentemente dall'impostazione di dpi. Ad esempio, la proprietà <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> restituisce in genere le coordinate logiche. Se si sposta il cursore su un elemento in una finestra di dialogo, vengono restituite le stesse coordinate indipendentemente dall'impostazione di dpi. Se si disegna un controllo in corrispondenza di (100, 100), viene disegnato in tali coordinate logiche e occuperà la stessa posizione relativa in qualsiasi impostazione dpi.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>
## <a name="scaling-in-ui-automation-clients"></a>Ridimensionamento nei client di automazione interfaccia utente  
 L'API [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non utilizza coordinate logiche. I metodi e le proprietà seguenti restituiscono coordinate fisiche o le accettano come parametri.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 Per impostazione predefinita, un'applicazione client di automazione interfaccia utente in esecuzione in un ambiente non-96- dpi non sarà in grado di ottenere risultati corretti da questi metodi e proprietà. Ad esempio, poiché la posizione del cursore è definita in coordinate logiche, il client non può semplicemente passare tali coordinate al metodo <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> per ottenere l'elemento sotto il cursore. Inoltre, l'applicazione non sarà in grado di posizionare correttamente le finestre al di fuori dell'area client.  
  
 La soluzione è costituita da due parti.  
  
1. In primo luogo, rendere l'applicazione client dpi-aware. A tale scopo, chiamare la `SetProcessDPIAware` funzione Win32 all'avvio. In codice gestito, la dichiarazione seguente rende disponibile questa funzione.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Questa funzione rende l'intero processo dpi-aware, vale a dire che tutte le finestre che appartengono al processo non vengono scalate. [Nell'esempio Evidenziatore](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), ad esempio, le quattro finestre che costituiscono il rettangolo di evidenziazione si trovano in corrispondenza delle coordinate fisiche ottenute da Automazione interfaccia utenteUI Automation, non delle coordinate logiche. Se l'esempio non fosse dpi-aware, l'evidenziazione verrebbe disegnata in corrispondenza delle coordinate logiche sul desktop, il che comporterebbe un posizionamento non corretto in un ambiente non-96- dpi.  
  
2. Per ottenere le coordinate del cursore, chiamare la funzione `GetPhysicalCursorPos`Win32 . Nell'esempio riportato di seguito viene illustrato come dichiarare e usare questa funzione.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> Non usare <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Il comportamento di questa proprietà al di fuori delle finestre client in un ambiente non ridimensionato non è definito.  
  
 Se l'applicazione esegue una comunicazione diretta tra processi con applicazioni non in grado di riconoscere dpi, è possibile che sia stata eseguita la conversione tra coordinate logiche e fisiche utilizzando le funzioni `PhysicalToLogicalPoint` Win32 e `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>Vedere anche

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
