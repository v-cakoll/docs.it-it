---
title: Cenni preliminari sulle animazioni personalizzate
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes [WPF], animation
- key frames [WPF], custom
- custom key frames [WPF]
- animation [WPF], custom classes
- custom animation classes [WPF]
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
ms.openlocfilehash: 5a9ca51b87f73a24b90d0bd843ee306f8a1b970a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453091"
---
# <a name="custom-animations-overview"></a>Cenni preliminari sulle animazioni personalizzate
Questo argomento descrive come e quando estendere il sistema di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creando fotogrammi chiave e classi di animazione personalizzati o usando il callback per frame come alternativa al sistema.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere l'argomento, è necessario conoscere i diversi tipi di animazione offerti da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per altre informazioni, vedere Cenni preliminari sulle animazioni From/To/By, [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) e [Panoramica sulle animazioni tracciato](path-animations-overview.md).  
  
 Poiché le classi di animazione ereditano dalla classe <xref:System.Windows.Freezable>, è necessario avere familiarità con <xref:System.Windows.Freezable> oggetti e come ereditare da <xref:System.Windows.Freezable>. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Estensione del sistema di animazione  
 Esistono diversi modi per estendere il sistema di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], a seconda del livello di funzionalità incorporate che si desidera usare.  Esistono tre punti di estendibilità principali nel motore di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Creare un oggetto fotogramma chiave personalizzato ereditando da uno dei *tipi di\<>* classi del fotogramma chiave, ad esempio <xref:System.Windows.Media.Animation.DoubleKeyFrame>. Questo approccio usa la maggior parte delle funzionalità incorporate del motore di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Creare una classe di animazione personalizzata ereditando da <xref:System.Windows.Media.Animation.AnimationTimeline> o da uno dei *tipi di\<>* le classi AnimationBase.  
  
- Usare il callback per frame per generare animazioni per frame. Questo approccio ignora completamente il sistema di animazione e di intervalli.  
  
 La tabella seguente descrive alcuni scenari per l'estensione del sistema di animazione.  
  
|Quando si vuole...|Usare questo approccio|  
|-------------------------|-----------------------|  
|Personalizzare l'interpolazione tra valori di un tipo che possiede un *\<Tipo>* AnimationUsingKeyFrames corrispondente.|Creare un fotogramma chiave personalizzato. Per altre informazioni, vedere la sezione [Creare un fotogramma chiave personalizzato](#createacustomkeyframe).|  
|Non personalizzare solo l'interpolazione tra valori di un tipo che possiede un *\<Tipo>* Animation corrispondente.|Creare una classe di animazione personalizzata che eredita dalla classe *\<Tipo>* AnimationBase che corrisponde al tipo che si desidera animare. Per altre informazioni, vedere la sezione [Create a Custom Animation Class](#createacustomanimationtype) (Creare una classe di animazione personalizzata).|  
|Animare un tipo che non possiede alcuna animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondente.|Usare un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> o creare una classe che erediti da <xref:System.Windows.Media.Animation.AnimationTimeline>. Per altre informazioni, vedere la sezione [Create a Custom Animation Class](#createacustomanimationtype) (Creare una classe di animazione personalizzata).|  
|Animare più oggetti con valori che vengono calcolati a ogni frame e si basano l'ultimo set di interazioni tra oggetti.|Usare il callback per frame. Per altre informazioni, vedere la sezione [Usare il callback per frame](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Creare un fotogramma chiave personalizzato  
 La creazione di una classe di fotogramma chiave personalizzata rappresenta il modo più semplice per estendere il sistema di animazione. È consigliabile usare questo approccio quando si desidera usare un metodo di interpolazione diverso per un'animazione con fotogrammi chiave.  Come descritto in [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md), un'animazione con fotogrammi chiave usa oggetti fotogramma chiave per generare i valori di output. Ogni oggetto fotogramma chiave esegue tre funzioni:  
  
- Specifica un valore di destinazione usando la relativa proprietà <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
- Specifica l'ora in cui deve essere raggiunto il valore utilizzando la relativa proprietà <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
- Crea un'interpolazione tra il valore del fotogramma chiave precedente e il proprio valore implementando il metodo InterpolateValueCore.  
  
 **Istruzioni per l'implementazione**  
  
 Eseguire la derivazione dalla classe astratta *\<Tipo>* KeyFrame e implementare il metodo InterpolateValueCore. Il metodo InterpolateValueCore restituisce il valore corrente del fotogramma chiave. Accetta due parametri: il valore del fotogramma chiave precedente e un valore di avanzamento compreso tra 0 e 1. Lo stato 0 indica che il fotogramma chiave è appena iniziato e il valore 1 indica che il fotogramma chiave è stato appena completato e deve restituire il valore specificato dalla relativa proprietà <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
 Poiché il *tipo\<>* le classi del fotogramma chiave ereditano dalla classe <xref:System.Windows.Freezable>, è necessario eseguire l'override anche di <xref:System.Windows.Freezable.CreateInstanceCore%2A> core per restituire una nuova istanza della classe. Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Dopo aver creato l'animazione *\<Tipo>* KeyFrame personalizzata, è possibile usarla con *\<Tipo>* AnimationUsingKeyFrames per tale tipo.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Creare una classe di animazione personalizzata  
 La creazione di un tipo di animazione personalizzato consente un maggiore controllo sul modo in cui un oggetto viene animato. Esistono due modi consigliati per creare un tipo di animazione personalizzato: è possibile derivare dalla classe <xref:System.Windows.Media.Animation.AnimationTimeline> o dal *tipo di\<>* classe AnimationBase. La derivazione della classe *\<Tipo>* Animation o *\<Tipo>* AnimationUsingKeyFrames non è consigliata.  
  
### <a name="derive-from-typeanimationbase"></a>Derivazione dalla classe \<Tipo>AnimationBase  
 La derivazione da una classe *\<Tipo>* AnimationBase è il modo più semplice per creare un nuovo tipo di animazione. Usare questo approccio quando si desidera creare una nuova animazione per il tipo che dispone già di una classe *\<Tipo>* AnimationBase.  
  
 **Istruzioni per l'implementazione**  
  
 Eseguire la derivazione di una classe *\<Tipo>* Animation e implementare il metodo GetCurrentValueCore. Il metodo GetCurrentValueCore restituisce il valore corrente dell'animazione. Accetta tre parametri: un valore iniziale suggerito, un valore finale suggerito e un <xref:System.Windows.Media.Animation.AnimationClock>, che consente di determinare lo stato di avanzamento dell'animazione.  
  
 Poiché il *tipo\<>* le classi AnimationBase ereditano dalla classe <xref:System.Windows.Freezable>, è necessario eseguire l'override anche di <xref:System.Windows.Freezable.CreateInstanceCore%2A> core per restituire una nuova istanza della classe. Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per altri informazioni, vedere la documentazione relativa al metodo GetCurrentValueCore per la classe *\<Tipo>* AnimationBase per il tipo che si desidera animare. Per un esempio, vedere [Esempio di animazione personalizzata](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **Approcci alternativi**  
  
 Se si desidera semplicemente modificare il modo in cui i valori dell'animazione vengono interpolati, si prenda in considerazione la derivazione da una delle classi *\<Tipo>* KeyFrame. Il fotogramma chiave creato può essere usato con la classe *\<Tipo>* AnimationUsingKeyFrames corrispondente fornita da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="derive-from-animationtimeline"></a>Derivazione dalla classe AnimationTimeline  
 Derivare dalla classe <xref:System.Windows.Media.Animation.AnimationTimeline> quando si desidera creare un'animazione per un tipo che non dispone già di un'animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondente o si desidera creare un'animazione non fortemente tipizzata.  
  
 **Istruzioni per l'implementazione**  
  
 Derivare dalla classe <xref:System.Windows.Media.Animation.AnimationTimeline> ed eseguire l'override dei membri seguenti:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>: se la nuova classe è concreta, è necessario eseguire l'override di <xref:System.Windows.Freezable.CreateInstanceCore%2A> per restituire una nuova istanza della classe.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>: eseguire l'override di questo metodo per restituire il valore corrente dell'animazione. Accetta tre parametri: un valore di origine predefinito, un valore di destinazione predefinito e un <xref:System.Windows.Media.Animation.AnimationClock>. Utilizzare il <xref:System.Windows.Media.Animation.AnimationClock> per ottenere l'ora corrente o lo stato di avanzamento dell'animazione. L'uso dei valori predefiniti di origine e destinazione è facoltativo.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>: eseguire l'override di questa proprietà per indicare se l'animazione usa il valore di destinazione predefinito specificato dal metodo <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>: eseguire l'override di questa proprietà per indicare la <xref:System.Type> dell'output prodotto dall'animazione.  
  
 Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Il paradigma consigliato (usato dalle animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) consiste nell'usare due livelli di ereditarietà:  
  
1. Creare un *tipo di\<astratto >* classe AnimationBase che deriva da <xref:System.Windows.Media.Animation.AnimationTimeline>. Questa classe deve eseguire l'override del metodo <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>. Deve inoltre introdurre un nuovo metodo astratto, GetCurrentValueCore ed eseguire l'override <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> in modo che convalidi i tipi del valore di origine predefinito e dei parametri predefiniti del valore di destinazione, quindi chiama GetCurrentValueCore.  
  
2. Creare un'altra classe che eredita dal nuovo *tipo di\<>* classe AnimationBase ed esegue l'override del metodo <xref:System.Windows.Freezable.CreateInstanceCore%2A>, del metodo GetCurrentValueCore introdotto e della proprietà <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>.  
  
 **Approcci alternativi**  
  
 Se si vuole animare un tipo che non ha un'animazione from/to/by corrispondente o un'animazione con fotogrammi chiave, provare a usare un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>. Poiché è debolmente tipizzato, un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> può animare qualsiasi tipo di valore. Lo svantaggio di questo approccio è che <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> supporta solo l'interpolazione discreta.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Usare il callback per frame  
 Usare questo approccio quando è necessario ignorare completamente il sistema di animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Uno scenario di questo approccio è rappresentato dalle animazioni fisiche, dove a ciascun passaggio dell'animazione è necessario ricalcolare una nuova direzione o posizione degli oggetti animati in base all'ultima serie di interazioni dell'oggetto.  
  
 **Istruzioni per l'implementazione**  
  
 A differenza degli altri approcci descritti in questa panoramica, per usare un callback per frame non è necessario creare un'animazione personalizzata o una classe con fotogrammi chiave.  
  
 Viene invece registrato per l'evento <xref:System.Windows.Media.CompositionTarget.Rendering> dell'oggetto che contiene gli oggetti a cui si desidera aggiungere un'animazione. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sull'albero di composizione, viene chiamato il metodo del gestore eventi.  
  
 Nel gestore eventi eseguire i calcoli necessari per l'effetto di animazione e impostare le proprietà degli oggetti da animare con tali valori.  
  
 Per ottenere l'ora di presentazione del frame corrente, è possibile eseguire il cast delle <xref:System.EventArgs> associate a questo evento come <xref:System.Windows.Media.RenderingEventArgs>, che forniscono una proprietà <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> che è possibile usare per ottenere il tempo di rendering del frame corrente.  
  
 Per ulteriori informazioni, vedere la pagina <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Panoramica sulle animazioni tracciato](path-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Esempio di animazione personalizzata](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
