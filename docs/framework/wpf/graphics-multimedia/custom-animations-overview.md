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
ms.openlocfilehash: c5f315992e8ae37bc79602e6986d90e7af591fb2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186554"
---
# <a name="custom-animations-overview"></a>Cenni preliminari sulle animazioni personalizzate
Questo argomento descrive come e quando estendere il sistema di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creando fotogrammi chiave e classi di animazione personalizzati o usando il callback per frame come alternativa al sistema.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere l'argomento, è necessario conoscere i diversi tipi di animazione offerti da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per altre informazioni, vedere Cenni preliminari sulle animazioni From/To/By, [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) e [Panoramica sulle animazioni tracciato](path-animations-overview.md).  
  
 Poiché le classi <xref:System.Windows.Freezable> di animazione ereditano <xref:System.Windows.Freezable> dalla classe , <xref:System.Windows.Freezable>è necessario avere familiarità con gli oggetti e come ereditare da . Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>
## <a name="extending-the-animation-system"></a>Estensione del sistema di animazione  
 Esistono diversi modi per estendere il sistema di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], a seconda del livello di funzionalità incorporate che si desidera usare.  Esistono tre punti di estendibilità principali nel motore di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Creare un oggetto fotogramma chiave personalizzato * \< *ereditando da una delle <xref:System.Windows.Media.Animation.DoubleKeyFrame>classi Type>KeyFrame, ad esempio . Questo approccio usa la maggior parte delle funzionalità incorporate del motore di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Creare una classe di animazione personalizzata ereditando da <xref:System.Windows.Media.Animation.AnimationTimeline> o una delle * \< *classi Type>AnimationBase.  
  
- Usare il callback per frame per generare animazioni per frame. Questo approccio ignora completamente il sistema di animazione e di intervalli.  
  
 La tabella seguente descrive alcuni scenari per l'estensione del sistema di animazione.  
  
|Quando si vuole...|Usare questo approccio|  
|-------------------------|-----------------------|  
|Personalizzare l'interpolazione tra i valori di un tipo con un * \<oggetto corrispondente Type>* AnimationUsingKeyFramesCustomize the interpolation between values of a type that has a corresponding Type>AnimationUsingKeyFrames|Creare un fotogramma chiave personalizzato. Per altre informazioni, vedere la sezione [Creare un fotogramma chiave personalizzato](#createacustomkeyframe).|  
|Personalizzare più che la semplice interpolazione tra i valori di un tipo che dispone di un * \<tipo *corrispondente>'animazione.|Creare una classe di animazione personalizzata che eredita dal * \<Type>* AnimationBase classe che corrisponde al tipo che si desidera animare. Per altre informazioni, vedere la sezione [Create a Custom Animation Class](#createacustomanimationtype) (Creare una classe di animazione personalizzata).|  
|Animare un tipo che non possiede alcuna animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondente.|Utilizzare <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> o creare una classe <xref:System.Windows.Media.Animation.AnimationTimeline>che eredita da . Per altre informazioni, vedere la sezione [Create a Custom Animation Class](#createacustomanimationtype) (Creare una classe di animazione personalizzata).|  
|Animare più oggetti con valori che vengono calcolati a ogni frame e si basano l'ultimo set di interazioni tra oggetti.|Usare il callback per frame. Per altre informazioni, vedere la sezione [Usare il callback per frame](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>
## <a name="create-a-custom-key-frame"></a>Creare un fotogramma chiave personalizzato  
 La creazione di una classe di fotogramma chiave personalizzata rappresenta il modo più semplice per estendere il sistema di animazione. È consigliabile usare questo approccio quando si desidera usare un metodo di interpolazione diverso per un'animazione con fotogrammi chiave.  Come descritto in [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md), un'animazione con fotogrammi chiave usa oggetti fotogramma chiave per generare i valori di output. Ogni oggetto fotogramma chiave esegue tre funzioni:  
  
- Specifica un valore di <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> destinazione utilizzando la relativa proprietà.  
  
- Specifica il momento in cui tale valore <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> deve essere raggiunto utilizzando la relativa proprietà.  
  
- Crea un'interpolazione tra il valore del fotogramma chiave precedente e il proprio valore implementando il metodo InterpolateValueCore.  
  
 **Istruzioni per l'implementazione**  
  
 Derivare dal * \<Type>* KeyFrame classe astratta e implementare il InterpolateValueCore metodo. Il metodo InterpolateValueCore restituisce il valore corrente del fotogramma chiave. Accetta due parametri: il valore del fotogramma chiave precedente e un valore di avanzamento compreso tra 0 e 1. Un avanzamento pari a 0 indica che il fotogramma chiave è appena iniziato e il valore 1 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> indica che il fotogramma chiave è appena stato completato e deve restituire il valore specificato dalla relativa proprietà.  
  
 Poiché * \< *il Type>KeyFrame classi ereditano <xref:System.Windows.Freezable.CreateInstanceCore%2A> dalla <xref:System.Windows.Freezable> classe, è necessario eseguire anche l'override core per restituire una nuova istanza della classe. Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Dopo aver creato l'animazione * \<personalizzata Type>* KeyFrame, puoi usarlo con il * \<Type>* AnimationUsingKeyFrames per quel tipo.  
  
<a name="createacustomanimationtype"></a>
## <a name="create-a-custom-animation-class"></a>Creare una classe di animazione personalizzata  
 La creazione di un tipo di animazione personalizzato consente un maggiore controllo sul modo in cui un oggetto viene animato. Esistono due modi consigliati per creare un tipo <xref:System.Windows.Media.Animation.AnimationTimeline> di animazione personalizzato: è possibile derivare dalla classe o dal tipo>Classe AnimationBase.There are two recommended ways to create your own animation type: you can derive from the class or the * \<Type>* AnimationBase class. Non è consigliabile derivare dalle classi * \<Type>* Animation o * \<AnimationUsingKeyFrames.Deriving *from the Type a Animation or Type>AnimationUsingKeyFrames classes is not recommended.  
  
### <a name="derive-from-typeanimationbase"></a>Derivazione dalla classe \<Tipo>AnimationBase  
 Derivazione da * \< *un tipo>AnimationBase classe è il modo più semplice per creare un nuovo tipo di animazione. Utilizzare questo approccio quando si desidera creare una nuova animazione per il tipo che dispone già di una classe * \<Type>* AnimationBase corrispondente.  
  
 **Istruzioni per l'implementazione**  
  
 Derivare * \< *da un Type>Animation classe e implementare il GetCurrentValueCore metodo. Il metodo GetCurrentValueCore restituisce il valore corrente dell'animazione. Accetta tre parametri: un valore iniziale suggerito, un <xref:System.Windows.Media.Animation.AnimationClock>valore finale suggerito e un valore , che consente di determinare lo stato di avanzamento dell'animazione.  
  
 Poiché * \< *il Type>AnimationBase classi ereditano <xref:System.Windows.Freezable.CreateInstanceCore%2A> dalla <xref:System.Windows.Freezable> classe, è anche necessario eseguire l'override core per restituire una nuova istanza della classe. Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per altre informazioni, vedere la documentazione * \< *del metodo GetCurrentValueCore per la classe Type>AnimationBase per il tipo che si desidera animare. Per un esempio, vedere [Esempio di animazione personalizzata](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **Approcci alternativi**  
  
 Se si desidera semplicemente modificare la modalità di interpolazione dei * \< *valori di animazione, considerando la derivazione da una delle classi Type>KeyFrame. Il fotogramma chiave creato può essere utilizzato con il * \<tipo *corrispondente>AnimationUsingKeyFrames forniti da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="derive-from-animationtimeline"></a>Derivazione dalla classe AnimationTimeline  
 Derivare <xref:System.Windows.Media.Animation.AnimationTimeline> dalla classe quando si desidera creare un'animazione per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un tipo che non dispone già di un'animazione corrispondente o si desidera creare un'animazione non fortemente tipizzata.  
  
 **Istruzioni per l'implementazione**  
  
 Derivare <xref:System.Windows.Media.Animation.AnimationTimeline> dalla classe ed eseguire l'override dei seguenti membri:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>– Se la nuova classe è <xref:System.Windows.Freezable.CreateInstanceCore%2A> concreta, è necessario eseguire l'override per restituire una nuova istanza della classe.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>– Eseguire l'override di questo metodo per restituire il valore corrente dell'animazione. Accetta tre parametri: un valore di origine predefinito, <xref:System.Windows.Media.Animation.AnimationClock>un valore di destinazione predefinito e un valore di file . Utilizzare <xref:System.Windows.Media.Animation.AnimationClock> il per ottenere il tempo corrente o lo stato di avanzamento per l'animazione. L'uso dei valori predefiniti di origine e destinazione è facoltativo.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>– Eseguire l'override di questa proprietà per indicare se l'animazione utilizza il valore di destinazione predefinito specificato dal <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> metodo.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>– Eseguire l'override <xref:System.Type> di questa proprietà per indicare l'output prodotto dall'animazione.  
  
 Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Il paradigma consigliato (usato dalle animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) consiste nell'usare due livelli di ereditarietà:  
  
1. Creare un * \<oggetto *astratto Type><xref:System.Windows.Media.Animation.AnimationTimeline>AnimationBase classe che deriva da . Questa classe deve <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> eseguire l'override del metodo. Deve inoltre introdurre un nuovo metodo astratto, <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> GetCurrentValueCore, ed eseguire l'override in modo che convalidi i tipi del valore di origine predefinito e dei parametri del valore di destinazione, quindi chiami GetCurrentValueCore.It should also introduce a new abstract method, GetCurrentValueCore, and override so that it validates the types of the default origin value and default destination value parameters, then calls GetCurrentValueCore.  
  
2. Creare un'altra classe che * \< *eredita dalla nuova classe <xref:System.Windows.Freezable.CreateInstanceCore%2A> Type>AnimationBase ed esegue l'override <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> del metodo, del metodo GetCurrentValueCore introdotto e della proprietà.  
  
 **Approcci alternativi**  
  
 Se desiderate animare un tipo che non dispone di un'animazione From/To/By corrispondente o di un'animazione con fotogrammi chiave, considerate l'utilizzo di un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>oggetto . Poiché è debolmente <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> tipizzato, un oggetto può animare qualsiasi tipo di valore. Lo svantaggio di questo <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> approccio è che supporta solo l'interpolazione discreta.  
  
<a name="useperframecallback"></a>
## <a name="use-per-frame-callback"></a>Usare il callback per frame  
 Usare questo approccio quando è necessario ignorare completamente il sistema di animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Uno scenario di questo approccio è rappresentato dalle animazioni fisiche, dove a ciascun passaggio dell'animazione è necessario ricalcolare una nuova direzione o posizione degli oggetti animati in base all'ultima serie di interazioni dell'oggetto.  
  
 **Istruzioni per l'implementazione**  
  
 A differenza degli altri approcci descritti in questa panoramica, per usare un callback per frame non è necessario creare un'animazione personalizzata o una classe con fotogrammi chiave.  
  
 Al contrario, <xref:System.Windows.Media.CompositionTarget.Rendering> si registra per l'evento dell'oggetto che contiene gli oggetti che si desidera animare. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sull'albero di composizione, viene chiamato il metodo del gestore eventi.  
  
 Nel gestore eventi eseguire i calcoli necessari per l'effetto di animazione e impostare le proprietà degli oggetti da animare con tali valori.  
  
 Per ottenere l'ora di presentazione <xref:System.EventArgs> del fotogramma corrente, <xref:System.Windows.Media.RenderingEventArgs>è possibile <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> eseguire il cast dell'oggetto associato a questo evento come , che forniscono una proprietà che è possibile utilizzare per ottenere il tempo di rendering del fotogramma corrente.  
  
 Per ulteriori informazioni, <xref:System.Windows.Media.CompositionTarget.Rendering> vedere la pagina.  
  
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
