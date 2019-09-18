---
title: Direttiva x:Subclass
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: f6f02998a7648693bd731d6b2afdfd4499abaa04
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053904"
---
# <a name="xsubclass-directive"></a>Direttiva x:Subclass
Modifica il comportamento di compilazione del `x:Class` markup XAML quando viene fornito anche. Anziché creare una classe parziale basata su `x:Class`, l'oggetto fornito `x:Class` viene creato come classe intermedia, quindi la classe derivata fornita dovrebbe essere basata su `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`namespace`|facoltativo. Specifica uno spazio dei nomi CLR `classname`che contiene. Se `namespace` si specifica, un punto (.) `namespace` separa e `classname`.|  
|`classname`|Richiesto. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per il codice XAML. Vedere la sezione Osservazioni.|  
|`subclassNamespace`|facoltativo. Può essere diverso da `namespace` se ogni spazio dei nomi può risolvere l'altro. Specifica uno spazio dei nomi CLR `subclassName`che contiene. Se `subclassName` si specifica, un punto (.) `subclassNamespace` separa e `subclassName`.|  
|`subclassName`|Richiesto. Specifica il nome CLR della sottoclasse.|  
  
## <a name="dependencies"></a>Dependencies  
 è necessario fornire anche la [direttiva x:Class](x-class-directive.md) sullo stesso oggetto e tale oggetto deve essere l'elemento radice dell'ambiente di produzione XAML.  
  
## <a name="remarks"></a>Note  
 `x:Subclass`l'utilizzo è destinato principalmente a linguaggi che non supportano dichiarazioni di classe parziali.  
  
 La classe utilizzata come `x:Subclass` non può essere una classe annidata e `x:Subclass` deve fare riferimento all'oggetto radice come illustrato nella sezione "dipendenze".  
  
 In caso contrario, il significato `x:Subclass` concettuale di non è definito da un'implementazione dei servizi XAML .NET Framework. Questo perché .NET Framework comportamento dei servizi XAML non specifica il modello di programmazione generale in base al quale sono connessi il markup XAML e il codice di supporto. Le implementazioni di altri concetti correlati `x:Class` a `x:Subclass` e vengono eseguite da framework specifici che usano modelli di programmazione o modelli di applicazione per definire come connettere markup XAML, markup compilato e code-behind basato su CLR. Ogni Framework potrebbe disporre di proprie azioni di compilazione che abilitano parte del comportamento o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un Framework, le azioni di compilazione possono variare anche in base al linguaggio CLR specifico usato per il code-behind.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 `x:Subclass`può trovarsi in una radice della pagina o <xref:System.Windows.Application> nella radice nella definizione dell'applicazione, che ha `x:Class`già. La Dichiarazione `x:Class` di qualsiasi elemento diverso dalla radice di una pagina o di un'applicazione o di specificarla laddove non esiste, causa un errore in fase di compilazione. `x:Subclass`  
  
 La creazione di classi derivate che `x:Subclass` funzionano correttamente per lo scenario è piuttosto complessa. Potrebbe essere necessario esaminare i file intermedi, ovvero i file. g prodotti nella cartella obj del progetto tramite il markup Compile, con i nomi che incorporano i nomi di file con estensione XAML. Questi file intermedi consentono di determinare l'origine di determinati costrutti di programmazione nelle classi parziali unite in join nell'applicazione compilata.  
  
 I gestori eventi nella classe derivata devono essere `internal override` (`Friend Overrides` in Microsoft Visual Basic) per eseguire l'override degli stub per i gestori creati nella classe intermedia durante la compilazione. In caso contrario, le implementazioni della classe derivata nascondono (ombreggiatura) l'implementazione della classe intermedia e i gestori della classe intermedia non vengono richiamati.  
  
 Quando si definiscono sia `x:Class` `x:Subclass`che, non è necessario fornire alcuna implementazione per la classe a `x:Class`cui fa riferimento. È sufficiente assegnare un nome tramite l' `x:Class` attributo, in modo che il compilatore abbia alcune linee guida per la classe creata nei file intermedi. in questo caso il compilatore non seleziona un nome predefinito. È possibile assegnare alla `x:Class` classe un'implementazione. Tuttavia, questo non è lo scenario tipico per l' `x:Class` utilizzo di `x:Subclass`e.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Classi XAML e personalizzate per WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
