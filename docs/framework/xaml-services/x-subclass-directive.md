---
title: Direttiva x:Subclass
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: 20
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 566b772db0e8f96c3272481d47b3e220f727d95b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="xsubclass-directive"></a>Direttiva x:Subclass
Modifica il comportamento di compilazione markup XAML quando `x:Class` viene inoltre fornita. Anziché creare una classe parziale che si basa sul `x:Class`, forniti `x:Class` viene creata come una classe intermedia, e quindi la classe derivata è previsto che sia basata su `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`namespace`|Facoltativo. Specifica uno spazio dei nomi CLR che contiene `classname`. Se `namespace` è specificato, un punto (.) separa `namespace` e `classname`.|  
|`classname`|Obbligatorio. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per tale codice XAML. Vedere la sezione Osservazioni.|  
|`subclassNamespace`|Facoltativo. Può essere diverso da `namespace` se ogni spazio dei nomi è possibile risolvere l'altro. Specifica uno spazio dei nomi CLR che contiene `subclassName`. Se `subclassName` è specificato, un punto (.) separa `subclassNamespace` e `subclassName`.|  
|`subclassName`|Obbligatorio. Specifica il nome CLR della sottoclasse.|  
  
## <a name="dependencies"></a>Dipendenze  
 [Direttiva X:Class](../../../docs/framework/xaml-services/x-class-directive.md) necessario fornire anche sullo stesso oggetto, che deve essere l'elemento radice della produzione XAML.  
  
## <a name="remarks"></a>Note  
 `x:Subclass` utilizzo è destinato principalmente per le lingue che non supportano le dichiarazioni di classe parziale.  
  
 La classe utilizzata come il `x:Subclass` non può essere una classe annidata, e `x:Subclass` deve fare riferimento all'oggetto radice, come illustrato nella sezione "Dipendenze".  
  
 In caso contrario, il significato concettuale di `x:Subclass` non è definita da un'implementazione di servizi XAML di .NET Framework. In questo modo il comportamento di servizi XAML di .NET Framework non specifica il modello di programmazione generale mediante XAML markup e il codice di supporto sono connessi. Le implementazioni di ulteriormente i concetti relativi a `x:Class` e `x:Subclass` vengono eseguite da framework specifici che utilizzano modelli di programmazione o applicazione per definire come connettere markup XAML, markup compilato e codice basato su CLR. Ogni framework potrebbe disporre di operazioni di compilazione che abilitano alcuni comportamenti o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un framework di azioni di compilazione possono inoltre variare in base al linguaggio CLR specifico utilizzato per il code-behind.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 `x:Subclass` può essere in una radice della pagina o nel database di <xref:System.Windows.Application> radice nella definizione dell'applicazione, che dispone già di `x:Class`. Dichiarazione di `x:Subclass` su qualsiasi elemento diverso da una radice di un'applicazione o pagina o specificarla in cui non `x:Class` esiste, genera un errore in fase di compilazione.  
  
 Creazione di derivata classi che funzionano correttamente per il `x:Subclass` scenario è abbastanza complesso. Potrebbe essere necessario esaminare i file intermedi (vale a dire i file g prodotti nella cartella obj del progetto dalla compilazione del markup, con nomi che includono i nomi dei file con estensione XAML). Questi file intermedi consentono di determinare l'origine di determinati costrutti di programmazione in classi parziali associate nell'applicazione compilata.  
  
 Gestori di eventi nella classe derivata devono essere `internal override` (`Friend Overrides` in Microsoft Visual Basic) per eseguire l'override gli stub per i gestori creati nella classe intermedia durante la compilazione. In caso contrario, le implementazioni della classe derivata nascondono l'implementazione della classe intermedi e non vengono richiamati i gestori di classe intermedia.  
  
 Quando si definiscono gli oggetti `x:Class` e `x:Subclass`, non è necessario fornire alcuna implementazione per la classe a cui fa riferimento `x:Class`. È necessario assegnargli un nome tramite il `x:Class` attributo in modo che il compilatore dispone di alcune indicazioni per la classe che viene creato il file intermedio (il compilatore non seleziona un nome predefinito in questo caso). È possibile assegnare il `x:Class` un'implementazione della classe; tuttavia, non si tratta di uno scenario tipico per l'utilizzo di entrambi `x:Class` e `x:Subclass`.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Classi XAML e personalizzate per WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
