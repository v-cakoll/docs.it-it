---
title: Direttiva x:Members
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: ca42079c1c40a8fb3b1ddfc8f4a6f742768fa9e1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053761"
---
# <a name="xmembers-directive"></a>Direttiva x:Members
Include un set di membri definiti nel markup, che si applicano alla x:Class dell'elemento padre.  
  
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
|`oneOrMoreMembers`|Uno o più elementi oggetto che rappresentano le definizioni dei membri. Si `x:Property` tratta in genere di elementi oggetto. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Nell'implementazione dei servizi XAML .NET Framework non è disponibile alcuna classe sottostante o implementazione del membro sottostante per `x:Members`. `x:Members`membro XAML speciale che può esistere come membro di qualsiasi tipo. In un flusso di nodi XAML `x:Members` , è rappresentato come un membro `Members`denominato, dallo spazio dei nomi XAML del linguaggio XAML. Il membro `Members` contiene un elenco generico di sola lettura di `Member` oggetti. Nei markup tipici i singoli membri vengono specificati come `x:Property` elementi della proprietà. `x:Property`è un tipo più preciso specificamente per le proprietà dei tipi ed è assegnabile `x:Member`a. Per ulteriori informazioni, vedere [X:Property Directive](x-property-directive.md).  
  
 Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata. Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`. Tuttavia, il meccanismo per l'associazione di tipi e membri o per la creazione di definizioni dei membri dinamici non è supportato a livello di servizi XAML di .NET Framework. Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML. In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>x:Members per Windows Workflow Foundation  
 Per Windows Workflow Foundation, `x:Members` contiene i membri di un'attività personalizzata composta interamente in XAML o membri dinamici definiti da XAML per un ActivityDesigner con code-behind. `x:Class` deve essere specificato anche nell'elemento radice della produzione XAML. Non è un requisito a livello di servizi XAML di .NET Framework, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano attività personalizzate e il codice XAML di Windows Workflow Foundation in generale. `x:Members`deve essere il primo elemento figlio nel markup dell'elemento oggetto che dichiara `x:Class`.
