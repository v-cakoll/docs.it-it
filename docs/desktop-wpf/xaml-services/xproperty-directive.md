---
title: Direttiva x:Property
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: 2804ec935d0626cba9ef050f70a3266cf23bcce0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071409"
---
# <a name="xproperty-directive"></a>Direttiva x:Property

Dichiara una proprietà XAML nel markup.

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`className`|Nome della classe sottostante o della classe parziale per la produzione XAML.|
|`propertyName`|Nome membro della proprietà da definire.|
|`propertyType`|Nome del tipo (o altro formato stringa, specifico del framework) che specifica il tipo di questa proprietà.|

## <a name="remarks"></a>Osservazioni

Nell'implementazione dei servizi XAML .NET, . `x:Property` non dispone di un supporto del tipo diretto, ma è supportato dalla classe <xref:System.Windows.Markup.PropertyDefinition>. In un flusso del nodo XAML, un elemento `x:Property` viene rappresentato come membro denominato `Property`, dallo spazio dei nomi XAML del linguaggio XAML. Il membro `Property` contiene gli attributi dichiarati dal markup.

Il significato `Name` `Type` di e non vengono assegnati a livello di servizi XAML .NET. Vengono archiviati nel flusso del nodo XAML iniziale come valori di stringa, da interpretare in seguito in base alle regole che potrebbero essere imposte da framework specifici. Il significato potrebbe allinearsi al significato di un nome XAML e di un tipo XAML o potrebbe essere valido solo in un sistema di tipi di supporto, a seconda dell'implementazione.

Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata. Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`. Tuttavia, il meccanismo per associare tipi e membri o per la produzione di definizioni di membri dinamici non è supportato a livello di servizi XAML .NET. Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML. In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.

## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property per Windows Workflow Foundation

Per Windows Workflow Foundation, `x:Property` definisce i membri di un'attività personalizzata costituita interamente in XAML o i membri dinamici definiti da XAML per ActivityDesigner con code-behind. `x:Class` deve essere specificato anche nell'elemento radice della produzione XAML. Questo non è un requisito a livello di servizi XAML .NET, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano le attività personalizzate e XAML di Windows Workflow Foundation in generale. Windows Workflow Foundation non usa il nome del tipo `x:Property` `Type` XAML puro come valore previsto per l'attributo e utilizza invece una convenzione che non è documentata qui. Per ulteriori informazioni, vedere [Creazione dinamica dinamica](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).
