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
ms.openlocfilehash: 268d218097233aee795154226cc6f7c3ce318f5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010150"
---
# <a name="custom-animations-overview"></a>Cenni preliminari sulle animazioni personalizzate
Questo argomento descrive come e quando estendere il sistema di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creando fotogrammi chiave e classi di animazione personalizzati o usando il callback per frame come alternativa al sistema.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere l'argomento, è necessario conoscere i diversi tipi di animazione offerti da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per altre informazioni, vedere Cenni preliminari sulle animazioni From/To/By, [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) e [Panoramica sulle animazioni tracciato](path-animations-overview.md).  
  
 Poiché le classi di animazione ereditano dal <xref:System.Windows.Freezable> (classe), è necessario conoscere <xref:System.Windows.Freezable> gli oggetti e su come ereditare da <xref:System.Windows.Freezable>. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Estensione del sistema di animazione  
 Esistono diversi modi per estendere il sistema di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], a seconda del livello di funzionalità incorporate che si desidera usare.  Esistono tre punti di estendibilità principali nel motore di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Creare un oggetto fotogramma chiave personalizzato ereditando da una delle  *\<tipo >* classi fotogramma chiave, ad esempio <xref:System.Windows.Media.Animation.DoubleKeyFrame>. Questo approccio usa la maggior parte delle funzionalità incorporate del motore di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Creare una classe di animazione personalizzato ereditando da <xref:System.Windows.Media.Animation.AnimationTimeline> o uno dei  *\<tipo >* classi AnimationBase.  
  
- Usare il callback per frame per generare animazioni per frame. Questo approccio ignora completamente il sistema di animazione e di intervalli.  
  
 La tabella seguente descrive alcuni scenari per l'estensione del sistema di animazione.  
  
|Quando si vuole...|Usare questo approccio|  
|-------------------------|-----------------------|  
|Personalizzare l'interpolazione tra valori di un tipo che possiede un *\<Tipo>* AnimationUsingKeyFrames corrispondente.|Creare un fotogramma chiave personalizzato. Per altre informazioni, vedere la sezione [Creare un fotogramma chiave personalizzato](#createacustomkeyframe).|  
|Non personalizzare solo l'interpolazione tra valori di un tipo che possiede un *\<Tipo>* Animation corrispondente.|Creare una classe di animazione personalizzata che eredita dalla classe *\<Tipo>* AnimationBase che corrisponde al tipo che si desidera animare. Per altre informazioni, vedere la sezione [Create a Custom Animation Class](#createacustomanimationtype) (Creare una classe di animazione personalizzata).|  
|Animare un tipo che non possiede alcuna animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondente.|Usa un' <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> o creare una classe che eredita da <xref:System.Windows.Media.Animation.AnimationTimeline>. Per altre informazioni, vedere la sezione [Create a Custom Animation Class](#createacustomanimationtype) (Creare una classe di animazione personalizzata).|  
|Animare più oggetti con valori che vengono calcolati a ogni frame e si basano l'ultimo set di interazioni tra oggetti.|Usare il callback per frame. Per altre informazioni, vedere la sezione [Usare il callback per frame](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Creare un fotogramma chiave personalizzato  
 La creazione di una classe di fotogramma chiave personalizzata rappresenta il modo più semplice per estendere il sistema di animazione. È consigliabile usare questo approccio quando si desidera usare un metodo di interpolazione diverso per un'animazione con fotogrammi chiave.  Come descritto in [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md), un'animazione con fotogrammi chiave usa oggetti fotogramma chiave per generare i valori di output. Ogni oggetto fotogramma chiave esegue tre funzioni:  
  
- Specifica un valore di destinazione utilizzando il <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> proprietà.  
  
- Specifica l'ora in cui tale valore deve essere raggiunto utilizzando relativo <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> proprietà.  
  
- Crea un'interpolazione tra il valore del fotogramma chiave precedente e il proprio valore implementando il metodo InterpolateValueCore.  
  
 **Istruzioni per l'implementazione**  
  
 Eseguire la derivazione dalla classe astratta *\<Tipo>* KeyFrame e implementare il metodo InterpolateValueCore. Il metodo InterpolateValueCore restituisce il valore corrente del fotogramma chiave. Accetta due parametri: il valore del fotogramma chiave precedente e un valore di avanzamento compreso tra 0 e 1. Un avanzamento pari a 0 indica che il fotogramma chiave è appena stata avviata e un valore pari a 1 indica che il fotogramma chiave è appena stato completato e deve restituire il valore specificato dal relativo <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> proprietà.  
  
 Poiché il  *\<tipo >* KeyFrame eredita dal <xref:System.Windows.Freezable> (classe), è inoltre necessario sostituire <xref:System.Windows.Freezable.CreateInstanceCore%2A> core per restituire una nuova istanza della classe. Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Dopo aver creato l'animazione *\<Tipo>* KeyFrame personalizzata, è possibile usarla con *\<Tipo>* AnimationUsingKeyFrames per tale tipo.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Creare una classe di animazione personalizzata  
 La creazione di un tipo di animazione personalizzato consente un maggiore controllo sul modo in cui un oggetto viene animato. Esistono due modi consigliati per creare un proprio tipo di animazione: è possibile derivare il <xref:System.Windows.Media.Animation.AnimationTimeline> classe o il  *\<tipo >* classe AnimationBase. La derivazione della classe *\<Tipo>* Animation o *\<Tipo>* AnimationUsingKeyFrames non è consigliata.  
  
### <a name="derive-from-typeanimationbase"></a>Derivazione dalla classe \<Tipo>AnimationBase  
 La derivazione da una classe *\<Tipo>* AnimationBase è il modo più semplice per creare un nuovo tipo di animazione. Usare questo approccio quando si desidera creare una nuova animazione per il tipo che dispone già di una classe *\<Tipo>* AnimationBase.  
  
 **Istruzioni per l'implementazione**  
  
 Eseguire la derivazione di una classe *\<Tipo>* Animation e implementare il metodo GetCurrentValueCore. Il metodo GetCurrentValueCore restituisce il valore corrente dell'animazione. Accetta tre parametri: un valore iniziale suggerito, un valore finale suggerito e un <xref:System.Windows.Media.Animation.AnimationClock>, utilizzabile per determinare lo stato di avanzamento dell'animazione.  
  
 Poiché il  *\<tipo >* classi AnimationBase ereditano dal <xref:System.Windows.Freezable> (classe), è inoltre necessario sostituire <xref:System.Windows.Freezable.CreateInstanceCore%2A> core per restituire una nuova istanza della classe. Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per altri informazioni, vedere la documentazione relativa al metodo GetCurrentValueCore per la classe *\<Tipo>* AnimationBase per il tipo che si desidera animare. Per un esempio, vedere [Esempio di animazione personalizzata](https://go.microsoft.com/fwlink/?LinkID=159981)  
  
 **Approcci alternativi**  
  
 Se si desidera semplicemente modificare il modo in cui i valori dell'animazione vengono interpolati, si prenda in considerazione la derivazione da una delle classi *\<Tipo>* KeyFrame. Il fotogramma chiave creato può essere usato con la classe *\<Tipo>* AnimationUsingKeyFrames corrispondente fornita da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="derive-from-animationtimeline"></a>Derivazione dalla classe AnimationTimeline  
 Derivare dal <xref:System.Windows.Media.Animation.AnimationTimeline> classe quando si desidera creare un'animazione per un tipo che non dispone già di un oggetto corrispondente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'animazione o si vuole creare un'animazione che non sia fortemente tipizzata.  
  
 **Istruzioni per l'implementazione**  
  
 Derivativo di <xref:System.Windows.Media.Animation.AnimationTimeline> classe ed eseguire l'override dei membri seguenti:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A> : Se la nuova classe è concreta, è necessario eseguire l'override <xref:System.Windows.Freezable.CreateInstanceCore%2A> per restituire una nuova istanza della classe.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> : Eseguire l'override di questo metodo per restituire il valore corrente dell'animazione. Accetta tre parametri: un valore di origine predefinito, un valore di destinazione predefinito e un <xref:System.Windows.Media.Animation.AnimationClock>. Usare il <xref:System.Windows.Media.Animation.AnimationClock> per ottenere l'ora corrente o avanzamento dell'animazione. L'uso dei valori predefiniti di origine e destinazione è facoltativo.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> : Eseguire l'override di questa proprietà per indicare se l'animazione Usa il valore di destinazione predefinito specificato per il <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> (metodo).  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> : Eseguire l'override di questa proprietà per indicare il <xref:System.Type> di output prodotto dall'animazione.  
  
 Se la classe non usa le proprietà di dipendenza per archiviare i dati o richiede un'altra inizializzazione dopo la creazione, potrebbe essere necessario eseguire l'override di altri metodi. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Il paradigma consigliato (usato dalle animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) consiste nell'usare due livelli di ereditarietà:  
  
1. Creare una classe astratta  *\<tipo >* AnimationBase che deriva da <xref:System.Windows.Media.Animation.AnimationTimeline>. Questa classe deve eseguire l'override di <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> (metodo). Deve anche introdurre un nuovo metodo astratto, GetCurrentValueCore ed eseguire l'override <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> in modo che la convalida dei tipi dei parametri di valore di destinazione predefinito e valore di origine predefinito, quindi chiamare GetCurrentValueCore.  
  
2. Creare un'altra classe che eredita dalla nuova  *\<tipo >* classe AnimationBase ed esegue l'override di <xref:System.Windows.Freezable.CreateInstanceCore%2A> metodo, il metodo GetCurrentValueCore introdotto, e il <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> proprietà.  
  
 **Approcci alternativi**  
  
 Se si desidera aggiungere un'animazione a un tipo che non dispone di animazione From/To/By corrispondente o animazione con fotogrammi chiave, è consigliabile usare un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>. Poiché è scarsamente tipizzato, un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> può animare qualsiasi tipo di valore. Lo svantaggio di questo approccio è che <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> supporta solo l'interpolazione discreta.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Usare il callback per frame  
 Usare questo approccio quando è necessario ignorare completamente il sistema di animazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Uno scenario di questo approccio è rappresentato dalle animazioni fisiche, dove a ciascun passaggio dell'animazione è necessario ricalcolare una nuova direzione o posizione degli oggetti animati in base all'ultima serie di interazioni dell'oggetto.  
  
 **Istruzioni per l'implementazione**  
  
 A differenza degli altri approcci descritti in questa panoramica, per usare un callback per frame non è necessario creare un'animazione personalizzata o una classe con fotogrammi chiave.  
  
 Ma vengono registrati per il <xref:System.Windows.Media.CompositionTarget.Rendering> evento dell'oggetto che contiene gli oggetti da animare. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sull'albero di composizione, viene chiamato il metodo del gestore eventi.  
  
 Nel gestore eventi eseguire i calcoli necessari per l'effetto di animazione e impostare le proprietà degli oggetti da animare con tali valori.  
  
 Per ottenere l'ora di presentazione del frame corrente, il <xref:System.EventArgs> associato a questo evento può essere convertito come <xref:System.Windows.Media.RenderingEventArgs>, che forniscono un <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> ora di rendering del proprietà che è possibile usare per ottenere il frame corrente.  
  
 Per altre informazioni, vedere il <xref:System.Windows.Media.CompositionTarget.Rendering> pagina.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Panoramica sulle animazioni tracciato](path-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md)
- [Esempio di animazione personalizzata](https://go.microsoft.com/fwlink/?LinkID=159981)
