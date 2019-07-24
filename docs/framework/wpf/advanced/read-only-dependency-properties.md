---
title: Proprietà di dipendenza di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: aa6893b100311ead74f610dd20f327d130dff74a
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401644"
---
# <a name="read-only-dependency-properties"></a>Proprietà di dipendenza di sola lettura
Questo argomento descrive le proprietà di dipendenza di sola lettura, incluse le proprietà di dipendenza di sola lettura esistenti e gli scenari e le tecniche per la creazione di una proprietà di dipendenza di sola lettura personalizzata.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Nell'argomento si presuppone la conoscenza degli scenari di base dell'implementazione di una proprietà di dipendenza e del modo in cui i metadati vengono applicati a una proprietà di dipendenza personalizzata. Per il contesto, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md) e [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>Proprietà di dipendenza di sola lettura esistenti  
 Alcune delle proprietà di dipendenza definite nel framework [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono di sola lettura. La ragione più comune per specificare una proprietà di dipendenza di sola lettura è che si tratta di proprietà che devono essere usate per la determinazione dello stato. Se però lo stato è influenzato da una molteplicità di fattori, la semplice impostazione della proprietà su quello stato non rappresenta la soluzione appropriata nell'ottica della progettazione di un'interfaccia utente. La proprietà <xref:System.Windows.UIElement.IsMouseOver%2A> , ad esempio, sta semplicemente mostrando lo stato come determinato dall'input del mouse. Ogni tentativo di impostare questo valore a livello di codice aggirando il vero input del mouse sarebbe imprevedibile e potrebbe causare incongruenze.  
  
 Dal momento che non possono essere impostate, le proprietà di dipendenza di sola lettura non sono appropriate per molti degli scenari in cui in genere offrono una soluzione (vale a dire: data binding, possibilità di applicare direttamente uno stile a un valore, convalida, animazione, ereditarietà). Nonostante non possano essere impostate, queste proprietà hanno in ogni caso alcune delle funzionalità aggiuntive supportate dalle proprietà di dipendenza nel sistema di proprietà. La funzionalità più importante consiste nel fatto che la proprietà di dipendenza di sola lettura può essere usata come trigger di proprietà in uno stile. Non è possibile abilitare i trigger con una normale proprietà Common Language Runtime (CLR); deve essere una proprietà di dipendenza. La proprietà <xref:System.Windows.UIElement.IsMouseOver%2A> indicata sopra è un esempio perfetto di uno scenario in cui potrebbe essere molto utile definire uno stile per un controllo, in cui alcune proprietà visibili, ad esempio uno sfondo, un primo piano o proprietà simili di elementi compositi all'interno di il controllo cambierà quando l'utente posiziona il puntatore del mouse su un'area definita del controllo. Le modifiche a una proprietà di dipendenza di sola lettura possono anche essere rilevate e segnalate dai processi di invalidamento inerenti del sistema di proprietà, che infatti è dotato del supporto interno della funzionalità del trigger di proprietà.  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>Creazione di proprietà di dipendenza di sola lettura personalizzate  
 Assicurarsi di leggere la sezione precedente sui motivi per cui le proprietà di dipendenza di sola lettura non funzionano per molti scenari comuni di proprietà di dipendenza. Se tuttavia si ha uno scenario adatto, è possibile creare una proprietà di dipendenza di sola lettura personalizzata.  
  
 Gran parte del processo di creazione di una proprietà di dipendenza di sola lettura è identico a quello descritto negli argomenti [Proprietà di dipendenza personalizzate](custom-dependency-properties.md) e [Implementare una proprietà di dipendenza](how-to-implement-a-dependency-property.md). Vi sono tre differenze importanti:  
  
- Quando si registra la proprietà, chiamare il <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> metodo anziché il metodo normale <xref:System.Windows.DependencyProperty.Register%2A> per la registrazione della proprietà.  
  
- Quando si implementa la proprietà "wrapper" CLR, verificare che anche il wrapper non disponga di un'implementazione impostata, in modo che non vi sia alcuna incoerenza nello stato di sola lettura per il wrapper pubblico esposto.  
  
- L'oggetto restituito dalla registrazione di sola lettura è <xref:System.Windows.DependencyPropertyKey> <xref:System.Windows.DependencyProperty>anziché. Anche se è necessario archiviare il campo come membro, questo in genere non viene reso un membro pubblico del tipo.  
  
 Naturalmente, il valore o campo privato sottostante della proprietà di dipendenza di sola lettura può essere scritto usando qualsiasi logica. Tuttavia, il modo più semplice per impostare la proprietà inizialmente o come parte della logica di runtime consiste nell'usare le API del sistema di proprietà, anziché aggirare il sistema di proprietà e impostare direttamente il campo di supporto privato. In particolare, esiste una firma di <xref:System.Windows.DependencyObject.SetValue%2A> che accetta un parametro di tipo. <xref:System.Windows.DependencyPropertyKey> La modalità e la posizione in cui questo valore viene impostato a livello di codice all'interno della logica dell'applicazione influirà sulla modalità <xref:System.Windows.DependencyPropertyKey> di impostazione dell'accesso per l'oggetto creato al momento della prima registrazione della proprietà di dipendenza. Se si gestisce tutta questa logica all'interno della classe è possibile renderla privata o, se è necessario impostarla da un'altra porzione dell'assembly, è possibile impostarla come interna. Un approccio consiste nel chiamare <xref:System.Windows.DependencyObject.SetValue%2A> all'interno di un gestore eventi di classe di un evento pertinente che informa un'istanza della classe che è necessario modificare il valore della proprietà archiviata. Un altro approccio consiste nell'associare le proprietà di dipendenza utilizzando le <xref:System.Windows.PropertyChangedCallback> associazioni <xref:System.Windows.CoerceValueCallback> e i callback come parte dei metadati di tali proprietà durante la registrazione.  
  
 <xref:System.Windows.DependencyPropertyKey> Poiché è privato e non viene propagato dal sistema di proprietà all'esterno del codice, una proprietà di dipendenza di sola lettura ha una maggiore sicurezza dell'impostazione rispetto a una proprietà di dipendenza di lettura/scrittura. Per una proprietà di dipendenza di lettura e scrittura, il campo di identificazione è pubblico in modo esplicito oppure implicito, per cui la proprietà può essere impostata senza alcuna limitazione. Per informazioni più specifiche, vedere [Sicurezza della proprietà di dipendenza](dependency-property-security.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
