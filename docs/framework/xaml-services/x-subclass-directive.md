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
ms.openlocfilehash: 850fe8acf9e47149bd385e78b30e04ba77d7a8b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140790"
---
# <a name="xsubclass-directive"></a>Direttiva x:Subclass
Modifica il comportamento di compilazione XAML markup quando `x:Class` viene anche fornito. Anziché creare una classe parziale che si basa sul `x:Class`, l'oggetto fornito `x:Class` viene creata come una classe intermedia, e quindi è previsto che la classe derivata specificata in base a `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`namespace`|Facoltativo. Specifica uno spazio dei nomi CLR contenente `classname`. Se `namespace` viene specificato, un punto (.) separa `namespace` e `classname`.|  
|`classname`|Obbligatorio. Specifica il nome CLR della classe parziale che si connette il caricamento XAML e il code-behind per tale XAML. Vedere la sezione Osservazioni.|  
|`subclassNamespace`|Facoltativo. Può essere diversa dalla `namespace` se ogni spazio dei nomi può risolvere l'altra. Specifica uno spazio dei nomi CLR contenente `subclassName`. Se `subclassName` viene specificato, un punto (.) separa `subclassNamespace` e `subclassName`.|  
|`subclassName`|Obbligatorio. Specifica il nome CLR della sottoclasse.|  
  
## <a name="dependencies"></a>Dipendenze  
 [Direttiva X:Class](x-class-directive.md) deve anche essere specificato nello stesso oggetto, che deve essere l'elemento radice della produzione XAML.  
  
## <a name="remarks"></a>Note  
 `x:Subclass` utilizzo è destinato principalmente in linguaggi che non supportano le dichiarazioni di classe parziale.  
  
 La classe utilizzata come le `x:Subclass` non può essere una classe annidata, e `x:Subclass` deve fare riferimento all'oggetto radice, come illustrato nella sezione "Dipendenze".  
  
 In caso contrario, il significato di concettuale `x:Subclass` non è definito da un'implementazione di servizi XAML di .NET Framework. Questo avviene perché il comportamento dei servizi XAML di .NET Framework non specifica il modello di programmazione generale da cui XAML markup e il codice di supporto sono connessi. Le implementazioni di ulteriormente i concetti correlati a `x:Class` e `x:Subclass` vengono eseguite dal framework specifici che utilizzano modelli di programmazione o i modelli di applicazione per definire la modalità di connessione di markup XAML compilato markup e code-behind basati su CLR. Ogni framework potrebbe essere operazioni di compilazione che consentono alcuni dei comportamenti o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un framework, le azioni di compilazione possono variare anche in base al linguaggio specifico di CLR che viene usato per il code-behind.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 `x:Subclass` può essere in una radice della pagina o nel database di <xref:System.Windows.Application> radice nella definizione di applicazione, che ha già `x:Class`. La dichiarazione `x:Subclass` su qualsiasi elemento diverso da una radice di pagina o un'applicazione o la specifica, in cui non `x:Class` esiste, provoca un errore in fase di compilazione.  
  
 Creazione di derivate le classi che funzionano correttamente per il `x:Subclass` scenario è piuttosto complesso. Potrebbe essere necessario esaminare i file intermedi (i file g nella cartella obj del progetto generati dalla compilazione del markup, con nomi che includono i nomi dei file con estensione XAML). Questi file intermedi consente di determinare l'origine di determinati costrutti di programmazione in classi parziali unite nell'applicazione compilata.  
  
 I gestori di eventi nella classe derivata devono essere `internal override` (`Friend Overrides` in Microsoft Visual Basic) per eseguire l'override gli stub per i gestori nella classe intermedia creati durante la compilazione. In caso contrario, le implementazioni della classe derivata nascondono (ombreggiatura molto sfumata) dell'implementazione della classe intermedi e non vengono richiamati i gestori classi intermedia.  
  
 Quando si definiscono entrambi `x:Class` e `x:Subclass`, non è necessario fornire qualsiasi implementazione della classe che fa riferimento `x:Class`. È sufficiente assegnarle un nome tramite la `x:Class` attributo in modo che il compilatore contiene alcune indicazioni per la classe che crea i file intermedi (il compilatore non seleziona un nome predefinito in questo caso). È possibile assegnare il `x:Class` un'implementazione della classe; tuttavia, ciò non lo scenario tipico per l'utilizzo di entrambe `x:Class` e `x:Subclass`.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Classi XAML e personalizzate per WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
