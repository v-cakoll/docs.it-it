---
title: Attributo PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991433"
---
# <a name="presentationoptionsfreeze-attribute"></a>Attributo PresentationOptions:Freeze
Imposta lo <xref:System.Windows.Freezable.IsFrozen%2A> `true` stato su sull'elemento contenitore <xref:System.Windows.Freezable> . Il comportamento predefinito per <xref:System.Windows.Freezable> un oggetto `PresentationOptions:Freeze` senza l'attributo specificato <xref:System.Windows.Freezable.IsFrozen%2A> è `false` che è in fase di caricamento e dipende <xref:System.Windows.Freezable> dal comportamento generale in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
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
|`PresentationOptions`|Prefisso dello spazio dei nomi XML, che può essere qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0. Il prefisso `PresentationOptions` viene usato per scopi di identificazione in questa documentazione.|  
|`freezableElement`|Elemento che crea un'istanza di qualsiasi classe derivata <xref:System.Windows.Freezable>di.|  
  
## <a name="remarks"></a>Note  
 L' `Freeze` attributo è l'unico attributo o altro elemento `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` di programmazione definito nello spazio dei nomi XML. L' `Freeze` attributo esiste in questo particolare spazio dei nomi specifico, in modo che possa essere designato come ignorabile, usando l' [attributo MC: Ignorable](mc-ignorable-attribute.md) come parte delle dichiarazioni degli elementi radice. Il motivo per `Freeze` cui deve essere possibile ignorare è il fatto che non tutte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] le implementazioni del processore sono in grado <xref:System.Windows.Freezable> di bloccare un oggetto in fase di caricamento. questa funzionalità [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non fa parte della specifica.  
  
 La possibilità di elaborare l' `Freeze` attributo è incorporata in modo specifico [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nel processore che [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elabora le applicazioni compilate. L'attributo non è supportato da alcuna classe e la sintassi dell'attributo non è estendibile o modificabile. Se si implementa un processore personalizzato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , è possibile scegliere di eseguire il blocco del comportamento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del processore durante l'elaborazione `Freeze` dell'attributo <xref:System.Windows.Freezable> sugli elementi in fase di caricamento.  
  
 Qualsiasi valore per l' `Freeze` attributo diverso da `true` (senza distinzione tra maiuscole e minuscole) genera un errore in fase di caricamento. (Specificando `Freeze` l'attributo `false` come non è un errore, ma è già l'impostazione predefinita, pertanto l' `false` impostazione di su non esegue alcuna operazione).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Attributo mc:Ignorable](mc-ignorable-attribute.md)
