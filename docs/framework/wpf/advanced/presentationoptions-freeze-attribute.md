---
title: Attributo PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074662"
---
# <a name="presentationoptionsfreeze-attribute"></a>Attributo PresentationOptions:Freeze
Imposta il <xref:System.Windows.Freezable.IsFrozen%2A> torni allo stato `true` nel contenitore <xref:System.Windows.Freezable> elemento. Il comportamento predefinito per un <xref:System.Windows.Freezable> senza il `PresentationOptions:Freeze` attributo specificato è quello <xref:System.Windows.Freezable.IsFrozen%2A> viene `false` al tempo di caricamento e dipendente in generale <xref:System.Windows.Freezable> comportamento in fase di esecuzione.  
  
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
|`PresentationOptions`|Un prefisso di spazio dei nomi XML, che può essere qualsiasi stringa di prefisso valida, secondo la specifica XML 1.0. Il prefisso `PresentationOptions` viene usato per scopi di identificazione in questa documentazione.|  
|`freezableElement`|Un elemento che crea un'istanza di una classe derivata di <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Note  
 Il `Freeze` attributo è l'unico attributo o altri elementi di programmazione definito nel `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` spazio dei nomi XML. Il `Freeze` attributo è presente in questo spazio dei nomi speciale in particolare in modo che può essere definito come ignorable, usando [mc: attributo Ignorable](mc-ignorable-attribute.md) come parte di dichiarazioni dell'elemento radice. Il motivo che `Freeze` deve essere in grado di essere ignorabile è perché non tutti i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] le implementazioni del processore sono in grado di bloccare un <xref:System.Windows.Freezable> in fase di caricamento; questa funzionalità non è in parte il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specifica.  
  
 La possibilità di elaborare il `Freeze` attributo è stato compilato appositamente per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore che elabora [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per le applicazioni compilate. L'attributo non è supportato da qualsiasi classe, e la sintassi di attributo non è estendibile o modificabile. Se si implementa il proprio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore è possibile scegliere per il comportamento di blocco in parallelo il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore durante l'elaborazione il `Freeze` attributo <xref:System.Windows.Freezable> elementi in fase di caricamento.  
  
 Qualsiasi valore per il `Freeze` attributo diverso da `true` (non maiuscole / minuscole) genera un errore in fase di caricamento. (Specificare il `Freeze` dell'attributo come `false` non è un errore, ma che è già l'impostazione predefinita, pertanto l'impostazione `false` non esegue alcuna operazione).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Attributo mc:Ignorable](mc-ignorable-attribute.md)
