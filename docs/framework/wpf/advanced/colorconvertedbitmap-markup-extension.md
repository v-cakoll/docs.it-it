---
title: Estensione del markup ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: a5b491723a036c1b1fd0bb61736e6f2ee53fbcd3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141220"
---
# <a name="colorconvertedbitmap-markup-extension"></a>Estensione del markup ColorConvertedBitmap
Fornisce un modo per specificare un'origine bitmap che non dispone di un profilo incorporato. I contesti di colore/profili sono specificati dall'URI, così come l'URI di origine dell'immagine.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`imageSource`|URI della bitmap non profilata.|  
|`sourceIIC`|URI della configurazione del profilo di origine.|  
|`destinationIIC`|URI della configurazione del profilo di destinazione|  
  
## <a name="remarks"></a>Osservazioni  
 Questa estensione di markup è destinata a compilare un set correlato di valori di proprietà di <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>origine dell'immagine, ad esempio.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. `ColorConvertedBitmap`non è `ColorConvertedBitmapExtension`possibile usare (o) nella sintassi dell'elemento Property, perché i valori possono essere impostati solo come valori nel costruttore iniziale, che è la stringa che segue l'identificatore dell'estensione.  
  
 `ColorConvertedBitmap` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Cenni preliminari sulla creazione dell'immagine](../graphics-multimedia/imaging-overview.md)
