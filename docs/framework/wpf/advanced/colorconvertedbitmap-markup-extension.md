---
title: Estensione del markup ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: e8a36a1b8592146eb2474805638cdc3697adb0c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172939"
---
# <a name="colorconvertedbitmap-markup-extension"></a>Estensione del markup ColorConvertedBitmap
Fornisce un modo per specificare un'origine della bitmap che non dispone di un profilo incorporato. Contesti dei colori o i profili specificati da [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], come l'origine dell'immagine [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`imageSource`|Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] della bitmap non profilate.|  
|`sourceIIC`|Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] della configurazione del profilo di origine.|  
|`destinationIIC`|Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] della configurazione del profilo di destinazione|  
  
## <a name="remarks"></a>Note  
 Questa estensione di markup consente di riempire un set correlato di valori di proprietà di origine dell'immagine, ad esempio <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. `ColorConvertedBitmap` (o `ColorConvertedBitmapExtension`) non può essere utilizzato nella sintassi degli elementi proprietà, perché i valori possono essere impostati solo come valori nel costruttore iniziale, ovvero la stringa dopo l'identificatore dell'estensione.  
  
 `ColorConvertedBitmap` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Cenni preliminari sulla creazione dell'immagine](../graphics-multimedia/imaging-overview.md)
