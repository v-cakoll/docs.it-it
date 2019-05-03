---
title: Direttiva x:Members
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: d23e6b459af932e0a6f69309f26a1cce70a9d256
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938892"
---
# <a name="xmembers-directive"></a>Direttiva x:Members
Contiene un set di membri che sono definiti nel markup, che si applicano a X:Class dell'elemento padre.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
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
|`oneOrMoreMembers`|Uno o più elementi di oggetti che rappresentano le definizioni dei membri. Si tratta in genere `x:Property` elementi oggetto. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Nell'implementazione di servizi XAML di .NET Framework, non classe sottostante o implementazione del membro sottostanti per `x:Members`. `x:Members` è un membro XAML speciale che possono essere presenti come membro di qualsiasi tipo. In un flusso di nodi XAML, `x:Members` è rappresentato come un membro denominato `Members`, dello spazio dei nomi XAML del linguaggio XAML. Il membro `Members` contiene un elenco generico di sola lettura di `Member` oggetti. Nel markup tipica i singoli membri vengono specificati come `x:Property` elementi proprietà. `x:Property` è un tipo più preciso in modo specifico per le proprietà dei tipi ed è assegnabile a `x:Member`. Per altre informazioni, vedere [direttiva X:Property](x-property-directive.md).  
  
 Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata. Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`. Tuttavia, il meccanismo per l'associazione di tipi e membri o per la creazione di definizioni dei membri dinamici non è supportato a livello di servizi XAML di .NET Framework. Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML. In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>X:Members per Windows Workflow Foundation  
 Per Windows Workflow Foundation, `x:Members` contiene i membri di un'attività personalizzata costituita interamente in XAML o XAML: i membri dinamici per ActivityDesigner con code-behind definiti. `x:Class` deve essere specificato anche nell'elemento radice della produzione XAML. Non è un requisito a livello di servizi XAML di .NET Framework, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano attività personalizzate e il codice XAML di Windows Workflow Foundation in generale. `x:Members` deve essere il primo elemento figlio nel markup dell'elemento oggetto dichiara il `x:Class`.
