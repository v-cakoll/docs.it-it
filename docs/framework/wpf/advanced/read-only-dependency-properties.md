---
title: Proprietà di dipendenza di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: 8adc90182f0f42f52e6ace4e13c68acb3539516b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187177"
---
# <a name="read-only-dependency-properties"></a>Proprietà di dipendenza di sola lettura
Questo argomento descrive le proprietà di dipendenza di sola lettura, incluse le proprietà di dipendenza di sola lettura esistenti e gli scenari e le tecniche per la creazione di una proprietà di dipendenza di sola lettura personalizzata.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Nell'argomento si presuppone la conoscenza degli scenari di base dell'implementazione di una proprietà di dipendenza e del modo in cui i metadati vengono applicati a una proprietà di dipendenza personalizzata. Per il contesto, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md) e [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
<a name="existing"></a>
## <a name="existing-read-only-dependency-properties"></a>Proprietà di dipendenza di sola lettura esistenti  
 Alcune delle proprietà di dipendenza definite nel framework [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono di sola lettura. La ragione più comune per specificare una proprietà di dipendenza di sola lettura è che si tratta di proprietà che devono essere usate per la determinazione dello stato. Se però lo stato è influenzato da una molteplicità di fattori, la semplice impostazione della proprietà su quello stato non rappresenta la soluzione appropriata nell'ottica della progettazione di un'interfaccia utente. Ad esempio, <xref:System.Windows.UIElement.IsMouseOver%2A> la proprietà è in realtà solo lo stato di superficie come determinato dall'input del mouse. Ogni tentativo di impostare questo valore a livello di codice aggirando il vero input del mouse sarebbe imprevedibile e potrebbe causare incongruenze.  
  
 Dal momento che non possono essere impostate, le proprietà di dipendenza di sola lettura non sono appropriate per molti degli scenari in cui in genere offrono una soluzione (vale a dire: data binding, possibilità di applicare direttamente uno stile a un valore, convalida, animazione, ereditarietà). Nonostante non possano essere impostate, queste proprietà hanno in ogni caso alcune delle funzionalità aggiuntive supportate dalle proprietà di dipendenza nel sistema di proprietà. La funzionalità più importante consiste nel fatto che la proprietà di dipendenza di sola lettura può essere usata come trigger di proprietà in uno stile. Non è possibile abilitare i trigger con una normale proprietà DI Common Language Runtime (CLR); deve essere una proprietà di dipendenza. La proprietà di <xref:System.Windows.UIElement.IsMouseOver%2A> cui sopra è un esempio perfetto di uno scenario in cui potrebbe essere molto utile definire uno stile per un controllo, in cui alcune proprietà visibili, ad esempio uno sfondo, primo piano o proprietà simili di elementi compositi all'interno del controllo, cambieranno quando l'utente posiziona il mouse su un'area definita del controllo. Le modifiche a una proprietà di dipendenza di sola lettura possono anche essere rilevate e segnalate dai processi di invalidamento inerenti del sistema di proprietà, che infatti è dotato del supporto interno della funzionalità del trigger di proprietà.  
  
<a name="new"></a>
## <a name="creating-custom-read-only-dependency-properties"></a>Creazione di proprietà di dipendenza di sola lettura personalizzate  
 Assicurarsi di leggere la sezione precedente sui motivi per cui le proprietà di dipendenza di sola lettura non funzionano per molti scenari comuni di proprietà di dipendenza. Se tuttavia si ha uno scenario adatto, è possibile creare una proprietà di dipendenza di sola lettura personalizzata.  
  
 Gran parte del processo di creazione di una proprietà di dipendenza di sola lettura è identico a quello descritto negli argomenti [Proprietà di dipendenza personalizzate](custom-dependency-properties.md) e [Implementare una proprietà di dipendenza](how-to-implement-a-dependency-property.md). Vi sono tre differenze importanti:  
  
- Quando si registra la <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> proprietà, chiamare <xref:System.Windows.DependencyProperty.Register%2A> il metodo anziché il metodo normale per la registrazione della proprietà.  
  
- Quando si implementa la proprietà "wrapper" CLR, assicurarsi che anche il wrapper non disponga di un'implementazione impostata, in modo che non vi sia alcuna incoerenza nello stato di sola lettura per il wrapper pubblico esposto.  
  
- L'oggetto restituito dalla registrazione di <xref:System.Windows.DependencyPropertyKey> sola <xref:System.Windows.DependencyProperty>lettura è anziché . Anche se è necessario archiviare il campo come membro, questo in genere non viene reso un membro pubblico del tipo.  
  
 Naturalmente, il valore o campo privato sottostante della proprietà di dipendenza di sola lettura può essere scritto usando qualsiasi logica. Tuttavia, il modo più semplice per impostare la proprietà inizialmente o come parte della logica di runtime consiste nell'utilizzare le API del sistema di proprietà, anziché aggirare il sistema di proprietà e impostare direttamente il campo di supporto privato. In particolare, esiste una <xref:System.Windows.DependencyObject.SetValue%2A> firma che accetta <xref:System.Windows.DependencyPropertyKey>un parametro di tipo . Come e dove si imposta questo valore a livello di codice all'interno della logica dell'applicazione influirà su come si desidera impostare l'accesso su <xref:System.Windows.DependencyPropertyKey> creato quando è stata registrata la proprietà di dipendenza per la prima volta. Se si gestisce tutta questa logica all'interno della classe è possibile renderla privata o, se è necessario impostarla da un'altra porzione dell'assembly, è possibile impostarla come interna. Un approccio <xref:System.Windows.DependencyObject.SetValue%2A> consiste nel chiamare all'interno di un gestore eventi di classe di un evento rilevante che informa un'istanza della classe che il valore della proprietà archiviata deve essere modificato. Un altro approccio consiste nel unire le <xref:System.Windows.PropertyChangedCallback> <xref:System.Windows.CoerceValueCallback> proprietà di dipendenza usando i callback e associati come parte dei metadati di tali proprietà durante la registrazione.  
  
 Poiché <xref:System.Windows.DependencyPropertyKey> l'oggetto è privato e non viene propagato dal sistema di proprietà all'esterno del codice, una proprietà di dipendenza di sola lettura ha una maggiore sicurezza delle impostazioni rispetto a una proprietà di dipendenza di lettura/scrittura. Per una proprietà di dipendenza di lettura e scrittura, il campo di identificazione è pubblico in modo esplicito oppure implicito, per cui la proprietà può essere impostata senza alcuna limitazione. Per informazioni più specifiche, vedere [Sicurezza della proprietà di dipendenza](dependency-property-security.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
