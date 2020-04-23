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
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071367"
---
# <a name="xsubclass-directive"></a>Direttiva x:Subclass

Modifica il comportamento di compilazione del markup XAML quando `x:Class` viene fornito anche. Anziché creare una classe parziale basata su `x:Class`, il fornito `x:Class` viene creato come classe intermedia e quindi la classe derivata fornita deve essere basata su `x:Class`.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`namespace`|Facoltativa. Specifica uno spazio dei `classname`nomi CLR che contiene . Se `namespace` viene specificato, un punto `namespace` (.) separa e `classname`.|
|`classname`|Obbligatorio. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per tale codice XAML. Vedere la sezione Osservazioni.|
|`subclassNamespace`|Facoltativa. Può essere `namespace` diverso da se ogni spazio dei nomi può risolvere l'altro. Specifica uno spazio dei `subclassName`nomi CLR che contiene . Se `subclassName` viene specificato, un punto `subclassNamespace` (.) separa e `subclassName`.|
|`subclassName`|Obbligatorio. Specifica il nome CLR della sottoclasse.|

## <a name="dependencies"></a>Dependencies

[La direttiva x:Class](xclass-directive.md) deve essere fornita anche sullo stesso oggetto e tale oggetto deve essere l'elemento radice della produzione XAML.

## <a name="remarks"></a>Osservazioni

`x:Subclass`l'utilizzo è destinato principalmente ai linguaggi che non supportano le dichiarazioni di classe parziali.

La classe utilizzata `x:Subclass` come non può `x:Subclass` essere una classe annidata e deve fare riferimento all'oggetto radice come spiegato nella sezione "Dipendenze".

In caso contrario, il significato concettuale di non è definito da un'implementazione dei `x:Subclass` servizi XAML .NET. Ciò è dovuto al fatto che il comportamento dei servizi XAML .NET non specifica il modello di programmazione generale mediante il quale sono connessi il markup XAML e il codice di backup. Implementazioni di ulteriori `x:Class` concetti `x:Subclass` correlati e vengono eseguite da framework specifici che utilizzano modelli di programmazione o modelli di applicazione per definire come connettere il markup XAML, il markup compilato e il code-behind basato su CLR. Ogni framework potrebbe avere le proprie azioni di compilazione che consentono alcuni dei comportamenti o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un framework, le azioni di compilazione possono variare anche in base al linguaggio CLR specifico utilizzato per il code-behind.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

`x:Subclass`può trovarsi in una <xref:System.Windows.Application> radice di pagina o nella `x:Class`radice nella definizione dell'applicazione, che dispone già di . La `x:Subclass` dichiarazione su qualsiasi elemento diverso da una pagina `x:Class` o radice dell'applicazione o la specifica di dove non esiste, causa un errore in fase di compilazione.

La creazione di classi `x:Subclass` derivate che funzionano correttamente per lo scenario è piuttosto complessa. Potrebbe essere necessario esaminare i file intermedi (i file .g prodotti nella cartella obj del progetto dalla compilazione del markup, con nomi che incorporano i nomi dei file con estensione xaml). Questi file intermedi consentono di determinare l'origine di determinati costrutti di programmazione nelle classi parziali unite nell'applicazione compilata.

I gestori eventi nella `internal override` classe`Friend Overrides` derivata devono essere ( in Microsoft Visual Basic) per eseguire l'override degli stub per i gestori creati nella classe intermedia durante la compilazione. In caso contrario, le implementazioni della classe derivata nascondono (shadow) l'implementazione della classe intermedia e i gestori di classi intermedi non vengono richiamati.

Quando si `x:Class` definiscono both e `x:Subclass`, non è necessario fornire alcuna implementazione per la classe a cui fa riferimento `x:Class`. È sufficiente assegnargli un nome `x:Class` tramite l'attributo in modo che il compilatore disponga di alcune indicazioni per la classe creata nei file intermedi (in questo caso il compilatore non seleziona un nome predefinito). È possibile `x:Class` assegnare alla classe un'implementazione; tuttavia, questo non è lo `x:Class` `x:Subclass`scenario tipico per l'utilizzo di entrambi e .

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Classi XAML e personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
