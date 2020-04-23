---
title: Direttiva x:Members
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071465"
---
# <a name="xmembers-directive"></a>Direttiva x:Members
Contiene un set di membri definiti nel markup, che si applicano a x:Class dell'elemento padre.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`className`|Nome della classe sottostante o della classe parziale per la produzione XAML. Vedere la sezione Osservazioni.|
|`oneOrMoreMembers`|Uno o più elementi oggetto che rappresentano le definizioni dei membri. In genere, `x:Property` si tratta di elementi oggetto. Vedere la sezione Osservazioni.|

## <a name="remarks"></a>Osservazioni

Nell'implementazione dei servizi XAML .NET non esiste `x:Members`alcuna classe di backup o implementazione di membri sottostanti per . `x:Members`è un membro XAML speciale che può esistere come membro in qualsiasi tipo. In un flusso `x:Members` del nodo XAML, `Members`è rappresentato come membro denominato , dallo spazio dei nomi XAML del linguaggio XAML. Il `Members` membro contiene un elenco `Member` generico di oggetti di sola lettura. Nel markup tipico i singoli `x:Property` membri vengono specificati come elementi di proprietà. `x:Property`è un tipo più preciso specifico per le `x:Member`proprietà dei tipi ed è assegnabile a . Per ulteriori informazioni, vedere [Direttiva x:Property](xproperty-directive.md).

Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata. Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`. Tuttavia, il meccanismo per associare tipi e membri o per la produzione di definizioni di membri dinamici non è supportato a livello di servizi XAML .NET. Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML. In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.

## <a name="xmembers-for-windows-workflow-foundation"></a>x:Membri per Windows Workflow Foundation

Per Windows Workflow `x:Members` Foundation, contiene i membri di un'attività personalizzata composta interamente in XAML o membri dinamici definiti da XAML per un ActivityDesigner con code-behind. `x:Class` deve essere specificato anche nell'elemento radice della produzione XAML. Questo non è un requisito a livello di servizi XAML .NET, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano le attività personalizzate e XAML di Windows Workflow Foundation in generale. `x:Members`deve essere il primo elemento figlio nel markup `x:Class`dell'elemento oggetto che dichiara l'oggetto .
