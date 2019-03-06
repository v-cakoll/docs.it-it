---
title: Ereditarietà del valore della proprietà
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [WPF], property values
- value inheritance [WPF]
- properties [WPF], value inheritance
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
ms.openlocfilehash: 64cafbe2f6044c83600ef227608dee24b29e3943
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359880"
---
# <a name="property-value-inheritance"></a>Ereditarietà del valore della proprietà
L'ereditarietà del valore della proprietà è una funzionalità del sistema di proprietà [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. L'ereditarietà del valore della proprietà consente agli elementi figlio in un albero di elementi di ottenere il valore di una determinata proprietà dagli elementi padre, ereditando tale valore con le impostazioni specificate in un punto qualsiasi dell'elemento padre più vicino. Anche l'elemento padre potrebbe aver ottenuto il valore tramite l'ereditarietà del valore della proprietà, pertanto il sistema potrebbe procedere in modo ricorsivo fino alla radice della pagina. L'ereditarietà del valore della proprietà non è il comportamento predefinito del sistema di proprietà. È necessario stabilire una particolare impostazione dei metadati di una proprietà per fare in modo che quest'ultima attivi l'ereditarietà del valore per gli elementi figlio.  
  

  
<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## <a name="property-value-inheritance-is-containment-inheritance"></a>L'ereditarietà del valore della proprietà è un'ereditarietà di contenimento  
 Il termine "ereditarietà" usato in questa sede non coincide perfettamente con il concetto di ereditarietà nel contesto dei tipi e in generale della programmazione orientata a oggetti, in cui le classi derivate ereditano le definizioni dei membri dalle rispettive classi di base. Questo significato di ereditarietà è valido anche in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: le proprietà definite nelle varie classi di base sono esposte come attributi per le classi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] derivate, se usate come elementi ed esposte come membri per il codice. L'ereditarietà del valore della proprietà riguarda in particolare il modo in cui i valori delle proprietà possono ereditare da un elemento a un altro in base alle relazioni padre-figlio all'interno di un albero di elementi. L'albero di elementi è visibile più direttamente quando si annidano elementi all'interno di altri elementi in fase di definizione delle applicazioni nel markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Gli alberi di oggetti possono essere creati anche a livello di codice, aggiungendo oggetti a raccolte designate di altri oggetti. In questo caso la modalità di funzionamento dell'ereditarietà del valore della proprietà sarà la stessa nell'albero completato in fase di esecuzione.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## <a name="practical-applications-of-property-value-inheritance"></a>Applicazioni pratiche dell'ereditarietà del valore della proprietà  
 Le [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] includono diverse proprietà per cui è abilitata l'ereditarietà. In genere, lo scenario per queste proprietà prevede l'uso di una proprietà che possa essere impostata una sola volta per pagina, ma che sia anche un membro di una delle classi dell'elemento di base e quindi esista anche nella maggior parte degli elementi figlio. Ad esempio, il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà controlla la direzione propagata contenuto deve essere presentato e disposto nella pagina. Nella maggior parte dei casi si preferisce che il concetto di flusso del testo sia gestito coerentemente in tutti gli elementi figlio. Se per qualche motivo la direzione del flusso è stata reimpostata in un livello dell'albero di elementi dall'utente o dall'ambiente, la reimpostazione deve essere in genere eseguita per tutta la struttura. Quando il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà è abilitata l'ereditarietà, il valore debba solo essere impostare o reimpostare una sola volta a livello di nell'albero degli elementi che include i requisiti di presentazione di ogni pagina dell'applicazione. Anche il valore predefinito iniziale userà l'ereditarietà nello stesso modo. Il modello di ereditarietà del valore della proprietà consente in ogni caso ai singoli elementi di reimpostare il valore nelle rare occasioni in cui si sceglie intenzionalmente di usare una combinazione di direzioni di flusso.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## <a name="making-a-custom-property-inheritable"></a>Rendere ereditabile una proprietà personalizzata  
 Modificando i metadati di una proprietà personalizzata è possibile rendere ereditabili anche le proprietà di questo tipo. Si noti, tuttavia, che quando si definisce una proprietà come ereditabile è necessario fare alcune considerazioni sulle prestazioni. Nei casi in cui quella proprietà non dispone di un valore locale stabilito oppure di un valore ottenuto tramite stili, modelli o data binding, una proprietà ereditabile fornisce i relativi valori di proprietà assegnati a tutti gli elementi figlio dell'albero logico.  
  
 Per fare in modo che una proprietà partecipi all'ereditarietà del valore, creare una proprietà associata personalizzata, come descritto in [Registrare una proprietà associata](how-to-register-an-attached-property.md). Registrare la proprietà con i metadati (<xref:System.Windows.FrameworkPropertyMetadata>) e specificare l'opzione "Inherits" nelle impostazioni di opzioni all'interno dei metadati. Verificare quindi che la proprietà abbia un valore predefinito stabilito, perché quel valore sarà ereditato. Anche se la proprietà è stata registrata come associata, può essere necessario creare un "wrapper" della proprietà per ottenere o impostare l'accesso sul tipo di proprietario, come si farebbe per una proprietà di dipendenza non associata. Al termine dell'operazione, la proprietà ereditabile può essere impostata tramite il wrapper della proprietà diretto nel tipo di proprietario o i tipi derivati oppure può essere impostato utilizzando la sintassi della proprietà associata in qualsiasi <xref:System.Windows.DependencyObject>.  
  
 Le proprietà associate sono concettualmente simili alle proprietà globali. è possibile cercare il valore su qualsiasi <xref:System.Windows.DependencyObject> e ottenere un risultato valido. Lo scenario tipico per le proprietà associate consiste nell'impostare i valori delle proprietà sugli elementi figlio e tale scenario è più efficace se la proprietà in questione è una proprietà associata che è sempre implicitamente presente come proprietà associata su ogni elemento (<xref:System.Windows.DependencyObject>) nell'albero.  
  
> [!NOTE]
>  Anche se può sembrare che l'ereditarietà del valore della proprietà funzioni per le proprietà di dipendenza non associate, il comportamento di ereditarietà per una proprietà non associata tramite certi limiti di elementi nell'albero della fase di esecuzione non è definito. Usare sempre <xref:System.Windows.DependencyProperty.RegisterAttached%2A> per registrare le proprietà in cui si specificano <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> nei metadati.  
  
<a name="InheritanceContext"></a>   
## <a name="inheriting-property-values-across-tree-boundaries"></a>Eredità dei valori di proprietà attraverso i limiti dell'albero  
 L'ereditarietà delle proprietà funziona mediante il passaggio attraverso un albero di elementi. Quest'albero spesso è parallelo all'albero logico. Tuttavia, quando si include un oggetto di livello principale WPF nel markup che definisce un albero degli elementi, ad esempio un <xref:System.Windows.Media.Brush>, aver creato un albero logico discontinuo. Un vero albero logico non estende a livello concettuale i <xref:System.Windows.Media.Brush>, in quanto l'albero logico è un concetto a livello di framework WPF. È possibile verificarlo mostrate nei risultati quando si usano i metodi di <xref:System.Windows.LogicalTreeHelper>. Tuttavia, l'ereditarietà del valore della proprietà può colmare questa discontinuità nell'albero logico e comunque possibile passare i valori ereditati, purché la proprietà ereditabile è stata registrata come una proprietà associata e nessun limite di blocco dell'ereditarietà impostato intenzionalmente (ad esempio un <xref:System.Windows.Controls.Frame>) viene rilevato.  
  
## <a name="see-also"></a>Vedere anche
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Cenni preliminari sulle proprietà associate](attached-properties-overview.md)
- [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md)
