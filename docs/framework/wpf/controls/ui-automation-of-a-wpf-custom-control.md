---
title: Automazione interfaccia utenteUI Automation of a Custom Control
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
ms.openlocfilehash: 9c33d0e5da70820041ba2a2881082d9f7d179fc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187501"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Automazione interfaccia utente di un controllo personalizzato WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] fornisce una singola interfaccia generalizzata che i client di automazione possono usare per esaminare o gestire le interfacce utente di una varietà di piattaforme e framework. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] consente sia al codice di controllo di qualità (test) sia alle applicazioni di accessibilità, ad esempio le utilità per la lettura dello schermo, di esaminare gli elementi dell'interfaccia utente e simulare l'interazione dell'utente da altro codice. Per informazioni su [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] in tutte le piattaforme, vedere Accessibilità.  
  
 L'articolo descrive come implementare un provider di automazione interfaccia utente sul lato server per un controllo personalizzato che viene eseguito in un'applicazione WPF. WPF supporta [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] attraverso un albero di oggetti di automazione peer che affianca l'albero di elementi dell'interfaccia utente. Il codice di test e le applicazioni che forniscono funzionalità di accessibilità possono usare gli oggetti peer di automazione direttamente (per il codice in-process) o tramite l'interfaccia generalizzata fornita da [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  

<a name="AutomationPeerClasses"></a>
## <a name="automation-peer-classes"></a>Classi peer di automazione  
 I controlli [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] WPFWPF supportano una <xref:System.Windows.Automation.Peers.AutomationPeer>struttura ad albero di classi peer che derivano da . Per convenzione, i nomi delle classi peer iniziano con il nome della classe del controllo e terminano con "AutomationPeer". Ad esempio, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> è la <xref:System.Windows.Controls.Button> classe peer per la classe del controllo. Le classi peer sono [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] all'incirca equivalenti ai tipi di controllo, ma sono specifiche per gli elementi WPFWPF. Il codice di automazione che accede alle applicazioni WPF tramite l'interfaccia [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] non usa direttamente i peer di automazione, invece il codice di automazione nello stesso spazio di processo può usarli direttamente.  
  
<a name="BuiltInAutomationPeerClasses"></a>
## <a name="built-in-automation-peer-classes"></a>Classi peer di automazione integrate  
 Gli elementi implementano una classe peer di automazione se accettano l'attività dell'interfaccia da parte dell'utente o se contengono le informazioni necessarie per gli utenti di applicazioni per la lettura dello schermo. Non tutti gli oggetti visivi WPF dispongono di peer di automazione. Esempi di classi che implementano <xref:System.Windows.Controls.TextBox>peer <xref:System.Windows.Controls.Label>di automazione sono <xref:System.Windows.Controls.Button>, e . Esempi di classi che non implementano peer <xref:System.Windows.Controls.Decorator>di automazione sono classi che derivano da , <xref:System.Windows.Controls.Border>ad esempio , e classi basate su <xref:System.Windows.Controls.Panel>, quali <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.Canvas>.  
  
 La <xref:System.Windows.Controls.Control> classe base non dispone di una classe peer corrispondente. Se è necessario che una classe peer corrisponda <xref:System.Windows.Controls.Control>a un controllo personalizzato <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>che deriva da , è necessario derivare la classe peer personalizzata da .  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations-for-derived-peers"></a>Considerazioni sulla sicurezza per i peer derivati  
 I peer di automazione devono essere eseguiti in un ambiente parzialmente attendibile. Il codice nell'assembly UIAutomationClient non è configurato per l'esecuzione in un ambiente parzialmente attendibile e il codice di peer di automazione non deve fare riferimento a tale assembly. È consigliabile invece usare le classi nell'assembly UIAutomationTypes. Ad esempio, è <xref:System.Windows.Automation.AutomationElementIdentifiers> necessario utilizzare la classe dall'assembly <xref:System.Windows.Automation.AutomationElement> UIAutomationTypes, che corrisponde alla classe nell'assembly UIAutomationClient. Un modo sicuro consiste nel fare riferimento all'assembly UIAutomationTypes nel codice del peer di automazione.  
  
<a name="PeerNavigation"></a>
## <a name="peer-navigation"></a>Navigazione nel peer  
 Dopo aver individuato un peer di automazione, il codice <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> in-process può esplorare la struttura ad albero peer chiamando i metodi e <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> dell'oggetto. La navigazione tra gli elementi WPFWPF all'interno <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> di un controllo è supportata dall'implementazione del metodo da parte del peer. Il sistema di Automazione interfaccia utente chiama questo metodo per creare un albero di sottoelementi contenuti in un controllo, come ad esempio le voci di una casella di riepilogo. Il <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> metodo predefinito attraversa la struttura ad albero visuale di elementi per compilare la struttura ad albero dei peer di automazione. I controlli personalizzati eseguono l'override del metodo per esporre gli elementi figlio ai client di automazione, restituendo i peer di automazione di elementi che contengono informazioni o consentono l'interazione da parte dell'utente.  
  
<a name="Customizations"></a>
## <a name="customizations-in-a-derived-peer"></a>Personalizzazioni in un peer derivato  
 Tutte le classi <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> che derivano <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>da e contengono il metodo virtuale protetto . WPFWPF <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> chiama per ottenere l'oggetto peer di automazione per ogni controllo. Il codice di automazione può usare il peer per ottenere informazioni sulle funzionalità e le caratteristiche di un controllo e per simulare l'uso interattivo. Un controllo personalizzato che supporta <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> l'automazione deve eseguire l'override e restituire un'istanza di una classe che deriva da <xref:System.Windows.Automation.Peers.AutomationPeer>. Ad esempio, se un controllo <xref:System.Windows.Controls.Primitives.ButtonBase> personalizzato deriva dalla classe <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> , l'oggetto restituito da deve derivare da <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Quando si implementa un controllo personalizzato, è necessario eseguire l'override dei metodi "Core" dalla classe peer di automazione di base che descrivono il comportamento univoco e specifico del controllo personalizzato.  
  
### <a name="override-oncreateautomationpeer"></a>Override di OnCreateAutomationPeer  
 Eseguire <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> l'override del metodo per il controllo personalizzato in modo che <xref:System.Windows.Automation.Peers.AutomationPeer>restituisca l'oggetto provider, che deve derivare direttamente o indirettamente da .  
  
### <a name="override-getpattern"></a>Override di GetPattern  
 I peer di automazione semplificano alcuni aspetti dell'implementazione di provider [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] sul lato server, tuttavia i peer di automazione di controlli personalizzati devono comunque gestire le interfacce dei criteri. Analogamente ai provider non WPF, i peer supportano <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> i pattern <xref:System.Windows.Automation.Provider.IInvokeProvider>di controllo fornendo implementazioni di interfacce nello spazio dei nomi , ad esempio . Le interfacce dei criteri di controllo possono essere implementate dal peer stesso o da un altro oggetto. L'implementazione del <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> peer di restituisce l'oggetto che supporta il modello specificato. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]codice chiama <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> il metodo <xref:System.Windows.Automation.Peers.PatternInterface> e specifica un valore di enumerazione. L'override <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> di deve restituire l'oggetto che implementa il modello specificato. Se il controllo non dispone di un'implementazione personalizzata di un <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> modello, è possibile chiamare l'implementazione del tipo di base di per recuperare l'implementazione o null se il modello non è supportato per questo tipo di controllo. Ad esempio, un controllo NumericUpDown personalizzato può essere impostato [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] su un <xref:System.Windows.Automation.Provider.IRangeValueProvider> valore all'interno di un intervallo, pertanto il peer implementerebbe l'interfaccia. Nell'esempio seguente viene illustrato <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> come il metodo del <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> peer viene sottoposto a override per rispondere a un valore.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Un <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> metodo può anche specificare un sottoelemento come provider di modelli. Il codice seguente <xref:System.Windows.Controls.ItemsControl> mostra come trasferisce la <xref:System.Windows.Controls.ScrollViewer> gestione del pattern di scorrimento al peer del relativo controllo interno.  
  
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
  
 Per specificare un sottoelemento per la gestione del pattern, questo <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> codice ottiene <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> l'oggetto sottoelemento, crea un peer usando il metodo , imposta la proprietà del nuovo peer sul peer corrente e restituisce il nuovo peer. L'impostazione <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> su un sottoelemento impedisce la visualizzazione del sottoelemento nella struttura ad albero del peer <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>di automazione e definisce tutti gli eventi generati dal sottoelemento come originati dal controllo specificato in . Il <xref:System.Windows.Controls.ScrollViewer> controllo non viene visualizzato nell'albero di automazione e gli <xref:System.Windows.Controls.ItemsControl> eventi di scorrimento generati sembrano avere origine dall'oggetto.  
  
### <a name="override-core-methods"></a>Override dei metodi "Core"  
 Il codice di automazione ottiene informazioni sul controllo tramite chiamate a metodi pubblici della classe peer. Per fornire informazioni sul controllo, eseguire l'override di ogni metodo il cui nome termina con "Core" quando l'implementazione del controllo differisce da quella fornita dalla classe peer di automazione di base. Come minimo, il controllo <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> deve <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> implementare i metodi e , come illustrato nell'esempio seguente.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 L'implementazione di <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> descrive il <xref:System.Windows.Automation.ControlType> controllo restituendo un valore. Sebbene sia <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>possibile restituire , è necessario restituire uno dei tipi di controllo più specifici se descrive con precisione il controllo. Un valore <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> restituito di richiede lavoro [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]aggiuntivo [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] per il provider per implementare , e i prodotti client non sono in grado di anticipare la struttura di controllo, l'interazione con la tastiera e i possibili pattern di controllo.  
  
 Implementare <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> i metodi e per indicare se il controllo include contenuto di dati o svolge un ruolo interattivo nell'interfaccia utente (o entrambi). Per impostazione predefinita, entrambi i metodi restituiscono `true`. Queste impostazioni migliorano l'usabilità di strumenti di automazione, come le utilità per la lettura dello schermo, i quali possono usare questi metodi per filtrare l'albero di automazione. Se <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> il metodo trasferisce la gestione del modello a <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> un peer del sottoelemento, il metodo del peer del sottoelemento può restituire false per nascondere il peer del sottoelemento dall'albero di automazione. Ad esempio, lo <xref:System.Windows.Controls.ListBox> scorrimento in un <xref:System.Windows.Controls.ScrollViewer>oggetto viene gestito <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> da un <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> oggetto e <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> il peer <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>di automazione per viene restituito dal metodo dell'oggetto associato all'oggetto . Pertanto, <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> il <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> metodo `false`di restituisce , in modo che l'oggetto <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> non venga visualizzato nell'albero di automazione.  
  
 Il peer di automazione deve fornire valori predefiniti appropriati per il controllo. Tieni presente che il codice XAML che fa riferimento <xref:System.Windows.Automation.AutomationProperties> al tuo controllo può eseguire l'override delle implementazioni peer dei metodi principali includendo gli attributi. Il codice XAML seguente, ad esempio, crea un pulsante che dispone di due proprietà [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] personalizzate.  
  
```xaml  
<Button AutomationProperties.Name="Special"
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementare i provider di criteri  
 Le interfacce implementate da un provider personalizzato vengono dichiarate <xref:System.Windows.Controls.Control>in modo esplicito se l'elemento proprietario deriva direttamente da . Ad esempio, il codice seguente dichiara <xref:System.Windows.Controls.Control> un peer per un oggetto che implementa un valore di intervallo.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Se il controllo proprietario deriva da un tipo <xref:System.Windows.Controls.Primitives.RangeBase>specifico di controllo, ad esempio , il peer può essere derivato da una classe peer derivata equivalente. In questo caso, il <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>peer deriverebbe da , <xref:System.Windows.Automation.Provider.IRangeValueProvider>che fornisce un'implementazione di base di . Il codice seguente mostra la dichiarazione di un peer di questo tipo.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Per un'implementazione di esempio, vedere il codice sorgente di [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) o [C,](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) che implementa e utilizza un controllo personalizzato NumericUpDown.  
  
### <a name="raise-events"></a>Generare eventi  
 I client di automazione possono sottoscrivere eventi di automazione. I controlli personalizzati devono segnalare <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> le modifiche apportate allo stato del controllo chiamando il metodo . Analogamente, quando il valore <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> di una proprietà viene modificato, chiamare il metodo . Il codice seguente mostra come ottenere l'oggetto peer dall'interno del codice del controllo e chiamare un metodo per generare un evento. Per ottimizzare la procedura, il codice determina se sono presenti listener per questo tipo di evento. La generazione dell'evento solo in presenza di listener evita un sovraccarico inutile e consente al controllo di rimane pronto a rispondere.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su automazione interfaccia utente](../../ui-automation/ui-automation-overview.md)
- [Implementazione del provider di automazione interfaccia utente lato server](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [NumericUpDown (controllo personalizzato) (C ) su GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Controllo personalizzato NumericUpDown (Visual Basic) su GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
