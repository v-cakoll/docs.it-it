---
title: Direttiva x:Members
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: 2c273fce1f15d9a5af72bc3f5a530d3c26dfc77e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564136"
---
# <a name="xmembers-directive"></a>Direttiva x:Members
Contiene un set di membri che sono definiti nel markup, che si applicano alle X:Class dell'elemento padre.  
  
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
|`oneOrMoreMembers`|Uno o più elementi di oggetti che rappresentano le definizioni dei membri. In genere, questi sono `x:Property` elementi oggetto. Vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Nell'implementazione dei servizi XAML di .NET Framework, non è presente alcuna classe sottostante o l'implementazione sottostante di un membro per `x:Members`. `x:Members` è un membro XAML speciale che può esistere come membro di qualsiasi tipo. In un flusso del nodo XAML, `x:Members` è rappresentato come un membro denominato `Members`, spazio dei nomi XAML del linguaggio XAML. Il membro `Members` contiene un elenco generico di sola lettura di `Member` oggetti. Nel markup tipico i singoli membri vengono specificati come `x:Property` elementi proprietà. `x:Property` è un tipo in modo specifico per le proprietà dei tipi più preciso e può essere assegnata al `x:Member`. Per ulteriori informazioni, vedere [direttiva X:Property](../../../docs/framework/xaml-services/x-property-directive.md).  
  
 Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata. Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`. Tuttavia, il meccanismo per l'associazione di tipi e membri o per la creazione di definizioni dei membri dinamici non è supportato a livello di servizi XAML di .NET Framework. Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML. In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>x: i membri per Windows Workflow Foundation  
 Per Windows Workflow Foundation, `x:Members` contiene i membri di un'attività personalizzata costituita interamente in XAML o XAML: definiti membri dinamici di un ActivityDesigner con code-behind. `x:Class` deve essere specificato anche nell'elemento radice della produzione XAML. Non è un requisito a livello di servizi XAML di .NET Framework, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano attività personalizzate e il codice XAML di Windows Workflow Foundation in generale. `x:Members` deve essere il primo elemento figlio nel markup dell'elemento che dichiara il `x:Class`.
