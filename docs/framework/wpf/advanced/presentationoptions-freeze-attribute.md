---
title: Attributo PresentationOptions:Freeze
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8f1a876f65941afb159d4c3d8904ab4426d9177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="presentationoptionsfreeze-attribute"></a>Attributo PresentationOptions:Freeze
Imposta il <xref:System.Windows.Freezable.IsFrozen%2A> allo stato `true` nel contenitore <xref:System.Windows.Freezable> elemento. Il comportamento predefinito per un <xref:System.Windows.Freezable> senza il `PresentationOptions:Freeze` l'attributo specificato è che <xref:System.Windows.Freezable.IsFrozen%2A> è `false` in fase di caricamento e che dipendono dal generale <xref:System.Windows.Freezable> comportamento in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`PresentationOptions`|Un prefisso di spazio dei nomi XML, che può essere una stringa valida, secondo la specifica XML 1.0. Il prefisso `PresentationOptions` viene utilizzato per scopi di identificazione in questa documentazione.|  
|`freezableElement`|Un elemento che crea un'istanza di una classe derivata di <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Note  
 Il `Freeze` attributo è l'unico attributo o altri elementi di programmazione definito nel `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` spazio dei nomi XML. Il `Freeze` attributo esiste in questo spazio dei nomi speciale, in particolare, in modo che può essere definito come ignorable, utilizzando [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) come parte di dichiarazioni dell'elemento radice. Il motivo che `Freeze` deve essere in grado di essere impostato come ignorable è perché non tutti i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] le implementazioni del processore sono in grado di bloccare un <xref:System.Windows.Freezable> in fase di caricamento; questa funzionalità non è in parte il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specifica.  
  
 La possibilità di elaborare il `Freeze` attributo è stato compilato appositamente per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore che elabora [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per le applicazioni compilate. L'attributo non è supportato da qualsiasi classe e la sintassi di attributo non è estendibile o modificabile. Se si sta implementando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è possibile scegliere di parallela il comportamento di blocco del processore il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore durante l'elaborazione di `Freeze` attributo <xref:System.Windows.Freezable> elementi in fase di caricamento.  
  
 Qualsiasi valore per il `Freeze` attributo diverso da `true` (non maiuscole / minuscole) genera un errore in fase di caricamento. (Specificare il `Freeze` attributo `false` non è un errore, ma che è già il valore predefinito, pertanto l'impostazione `false` non esegue alcuna operazione).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Freezable>  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Attributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
