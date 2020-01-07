---
title: Automazione interfaccia utente di un controllo personalizzato WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: 1cafb6cf8fd5096e2c17d2687ec390db06faf873
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636068"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Automazione interfaccia utente di un controllo personalizzato WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] fornisce una singola interfaccia generalizzata che i client di automazione possono usare per esaminare o gestire le interfacce utente di una varietà di piattaforme e framework. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] consente sia al codice di controllo di qualità (test) sia alle applicazioni di accessibilità, ad esempio le utilità per la lettura dello schermo, di esaminare gli elementi dell'interfaccia utente e simulare l'interazione dell'utente da altro codice. Per informazioni su [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] in tutte le piattaforme, vedere Accessibilità.  
  
 L'articolo descrive come implementare un provider di automazione interfaccia utente sul lato server per un controllo personalizzato che viene eseguito in un'applicazione WPF. WPF supporta [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] attraverso un albero di oggetti di automazione peer che affianca l'albero di elementi dell'interfaccia utente. Il codice di test e le applicazioni che forniscono funzionalità di accessibilità possono usare gli oggetti peer di automazione direttamente (per il codice in-process) o tramite l'interfaccia generalizzata fornita da [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Classi peer di automazione  
 I controlli WPF supportano [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] tramite un albero di classi peer che derivano da <xref:System.Windows.Automation.Peers.AutomationPeer>. Per convenzione, i nomi delle classi peer iniziano con il nome della classe del controllo e terminano con "AutomationPeer". Ad esempio, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> è la classe peer per la classe del controllo <xref:System.Windows.Controls.Button>. Le classi peer sono approssimativamente equivalenti ai tipi di controllo [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] ma sono specifici degli elementi WPF. Il codice di automazione che accede alle applicazioni WPF tramite l'interfaccia [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] non usa direttamente i peer di automazione, invece il codice di automazione nello stesso spazio di processo può usarli direttamente.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Classi peer di automazione integrate  
 Gli elementi implementano una classe peer di automazione se accettano l'attività dell'interfaccia da parte dell'utente o se contengono le informazioni necessarie per gli utenti di applicazioni per la lettura dello schermo. Non tutti gli oggetti visivi WPF dispongono di peer di automazione. Esempi di classi che implementano i peer di automazione sono <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>e <xref:System.Windows.Controls.Label>. Esempi di classi che non implementano i peer di automazione sono classi che derivano da <xref:System.Windows.Controls.Decorator>, ad esempio <xref:System.Windows.Controls.Border>, e classi basate su <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.Canvas>.  
  
 La classe di base <xref:System.Windows.Controls.Control> non dispone di una classe peer corrispondente. Se è necessaria una classe peer che corrisponda a un controllo personalizzato che deriva da <xref:System.Windows.Controls.Control>, è necessario derivare la classe peer personalizzata da <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Considerazioni sulla sicurezza per i peer derivati  
 I peer di automazione devono essere eseguiti in un ambiente parzialmente attendibile. Il codice nell'assembly UIAutomationClient non è configurato per l'esecuzione in un ambiente parzialmente attendibile e il codice di peer di automazione non deve fare riferimento a tale assembly. È consigliabile invece usare le classi nell'assembly UIAutomationTypes. Ad esempio, è necessario usare la classe <xref:System.Windows.Automation.AutomationElementIdentifiers> dall'assembly UIAutomationTypes, che corrisponde alla classe <xref:System.Windows.Automation.AutomationElement> nell'assembly UIAutomationClient. Un modo sicuro consiste nel fare riferimento all'assembly UIAutomationTypes nel codice del peer di automazione.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Navigazione nel peer  
 Dopo aver individuato un peer di automazione, il codice in-process può spostarsi nell'albero del peer chiamando i metodi di <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> e <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> dell'oggetto. Lo spostamento tra elementi WPF all'interno di un controllo è supportato dall'implementazione del peer del <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> metodo. Il sistema di Automazione interfaccia utente chiama questo metodo per creare un albero di sottoelementi contenuti in un controllo, come ad esempio le voci di una casella di riepilogo. Il metodo <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> predefinito attraversa la struttura ad albero visuale degli elementi per compilare la struttura ad albero dei peer di automazione. I controlli personalizzati eseguono l'override del metodo per esporre gli elementi figlio ai client di automazione, restituendo i peer di automazione di elementi che contengono informazioni o consentono l'interazione da parte dell'utente.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Personalizzazioni in un peer derivato  
 Tutte le classi che derivano da <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement> contengono il metodo virtuale protetto <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF chiama <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> per ottenere l'oggetto peer di automazione per ogni controllo. Il codice di automazione può usare il peer per ottenere informazioni sulle funzionalità e le caratteristiche di un controllo e per simulare l'uso interattivo. Un controllo personalizzato che supporta l'automazione deve eseguire l'override di <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> e restituire un'istanza di una classe che deriva da <xref:System.Windows.Automation.Peers.AutomationPeer>. Se, ad esempio, un controllo personalizzato deriva dalla classe <xref:System.Windows.Controls.Primitives.ButtonBase>, l'oggetto restituito da <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> deve derivare da <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Quando si implementa un controllo personalizzato, è necessario eseguire l'override dei metodi "Core" dalla classe peer di automazione di base che descrivono il comportamento univoco e specifico del controllo personalizzato.  
  
### <a name="override-oncreateautomationpeer"></a>Override di OnCreateAutomationPeer  
 Eseguire l'override del metodo <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> per il controllo personalizzato in modo che restituisca l'oggetto provider, che deve derivare direttamente o indirettamente da <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Override di GetPattern  
 I peer di automazione semplificano alcuni aspetti dell'implementazione di provider [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] sul lato server, tuttavia i peer di automazione di controlli personalizzati devono comunque gestire le interfacce dei criteri. Come per i provider non WPF, i peer supportano i pattern di controllo fornendo le implementazioni delle interfacce nello spazio dei nomi <xref:System.Windows.Automation.Provider?displayProperty=nameWithType>, ad esempio <xref:System.Windows.Automation.Provider.IInvokeProvider>. Le interfacce dei criteri di controllo possono essere implementate dal peer stesso o da un altro oggetto. L'implementazione del peer di <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> restituisce l'oggetto che supporta il criterio specificato. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] codice chiama il metodo <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> e specifica un <xref:System.Windows.Automation.Peers.PatternInterface> valore di enumerazione. L'override di <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> deve restituire l'oggetto che implementa il pattern specificato. Se il controllo non dispone di un'implementazione personalizzata di un modello, è possibile chiamare l'implementazione del tipo di base di <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> per recuperare la relativa implementazione o null se il modello non è supportato per questo tipo di controllo. Un controllo NumericUpDown personalizzato, ad esempio, può essere impostato su un valore compreso in un intervallo, quindi il relativo [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] peer implementa l'interfaccia <xref:System.Windows.Automation.Provider.IRangeValueProvider>. Nell'esempio seguente viene illustrato come eseguire l'override del metodo <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> del peer per rispondere a un valore <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType>.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Un metodo <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> può inoltre specificare un sottoelemento come provider di criteri. Nel codice seguente viene illustrato il modo in cui <xref:System.Windows.Controls.ItemsControl> trasferisce la gestione dei pattern di scorrimento al peer del controllo <xref:System.Windows.Controls.ScrollViewer> interno.  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 Per specificare un sottoelemento per la gestione dei modelli, questo codice ottiene l'oggetto sottoelemento, crea un peer usando il metodo <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A>, imposta la proprietà <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> del nuovo peer sul peer corrente e restituisce il nuovo peer. L'impostazione di <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> su un sottoelemento impedisce la visualizzazione del sottoelemento nell'albero del peer di automazione e designa tutti gli eventi generati dal sottoelemento come originati dal controllo specificato in <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. Il controllo <xref:System.Windows.Controls.ScrollViewer> non viene visualizzato nell'albero di automazione e gli eventi di scorrimento generati sembrano avere origine dall'oggetto <xref:System.Windows.Controls.ItemsControl>.  
  
### <a name="override-core-methods"></a>Override dei metodi "Core"  
 Il codice di automazione ottiene informazioni sul controllo tramite chiamate a metodi pubblici della classe peer. Per fornire informazioni sul controllo, eseguire l'override di ogni metodo il cui nome termina con "Core" quando l'implementazione del controllo differisce da quella fornita dalla classe peer di automazione di base. Come minimo, il controllo deve implementare i metodi <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> e <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>, come illustrato nell'esempio seguente.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 L'implementazione di <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> descrive il controllo restituendo un valore <xref:System.Windows.Automation.ControlType>. Sebbene sia possibile restituire <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, è necessario restituire uno dei tipi di controllo più specifici se il controllo viene descritto in modo accurato. Un valore restituito di <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> richiede un lavoro aggiuntivo affinché il provider implementi [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]e [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] i prodotti client non siano in grado di prevedere la struttura del controllo, l'interazione da tastiera e i possibili pattern di controllo.  
  
 Implementare i metodi <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> e <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> per indicare se il controllo contiene contenuto dati o se soddisfa un ruolo interattivo nell'interfaccia utente (o entrambi). Per impostazione predefinita, entrambi i metodi restituiscono `true`. Queste impostazioni migliorano l'usabilità di strumenti di automazione, come le utilità per la lettura dello schermo, i quali possono usare questi metodi per filtrare l'albero di automazione. Se il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> trasferisce la gestione dei modelli a un peer di sottoelemento, il metodo di <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> del peer del sottoelemento può restituire false per nascondere il peer del sottoelemento dalla struttura ad albero di automazione. Ad esempio, lo scorrimento in un <xref:System.Windows.Controls.ListBox> viene gestito da un <xref:System.Windows.Controls.ScrollViewer>e il peer di automazione per <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> viene restituito dal metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> del <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> associato al <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Pertanto, il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> della <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> restituisce `false`, in modo che il <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> non venga visualizzato nell'albero di automazione.  
  
 Il peer di automazione deve fornire valori predefiniti appropriati per il controllo. Si noti che XAML che fa riferimento al controllo può eseguire l'override delle implementazioni peer dei metodi principali includendo <xref:System.Windows.Automation.AutomationProperties> attributi. Il codice XAML seguente, ad esempio, crea un pulsante che dispone di due proprietà [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] personalizzate.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementare i provider di criteri  
 Le interfacce implementate da un provider personalizzato vengono dichiarate in modo esplicito se l'elemento proprietario deriva direttamente da <xref:System.Windows.Controls.Control>. Il codice seguente, ad esempio, dichiara un peer per un <xref:System.Windows.Controls.Control> che implementa un valore di intervallo.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Se il controllo proprietario deriva da un tipo specifico di controllo, ad esempio <xref:System.Windows.Controls.Primitives.RangeBase>, il peer può essere derivato da una classe peer derivata equivalente. In questo caso, il peer deriverebbe da <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, che fornisce un'implementazione di base di <xref:System.Windows.Automation.Provider.IRangeValueProvider>. Il codice seguente mostra la dichiarazione di un peer di questo tipo.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Per un'implementazione di esempio, vedere [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) o [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) codice sorgente che implementa e utilizza un controllo personalizzato NumericUpDown.  
  
### <a name="raise-events"></a>Generare eventi  
 I client di automazione possono sottoscrivere eventi di automazione. I controlli personalizzati devono segnalare le modifiche allo stato del controllo chiamando il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A>. Analogamente, quando viene modificato il valore di una proprietà, chiamare il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A>. Il codice seguente mostra come ottenere l'oggetto peer dall'interno del codice del controllo e chiamare un metodo per generare un evento. Per ottimizzare la procedura, il codice determina se sono presenti listener per questo tipo di evento. La generazione dell'evento solo in presenza di listener evita un sovraccarico inutile e consente al controllo di rimane pronto a rispondere.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di automazione interfaccia utente](../../ui-automation/ui-automation-overview.md)
- [Implementazione del provider di automazione interfaccia utente lato server](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [Controllo personalizzato NumericUpDown (C#) su GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Controllo personalizzato NumericUpDown (Visual Basic) su GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
