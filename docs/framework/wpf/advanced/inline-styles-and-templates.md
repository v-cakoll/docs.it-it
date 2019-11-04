---
title: Stili e modelli inline
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460001"
---
# <a name="inline-styles-and-templates"></a>Stili e modelli inline
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce oggetti di <xref:System.Windows.Style> e oggetti modello (<xref:System.Windows.FrameworkTemplate> sottoclassi) come metodo per definire l'aspetto visivo di un elemento nelle risorse, in modo che possano essere utilizzate più volte. Per questo motivo, gli attributi in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che accettano i tipi <xref:System.Windows.Style> e <xref:System.Windows.FrameworkTemplate> quasi sempre fanno riferimento a risorse e modelli esistenti anziché definire nuovi modelli inline.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Limitazioni degli stili e dei modelli in linea  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le proprietà dello stile e del modello possono tecnicamente essere impostate in uno dei due modi. È possibile utilizzare la sintassi degli attributi per fare riferimento a uno stile definito all'interno di una risorsa, ad esempio `<`*oggetto*`Style="{StaticResource``}" .../>`*ResourceKey* . In alternativa, è possibile usare la sintassi dell'elemento Property per definire uno stile inline, ad esempio:  
  
 *oggetto* `<` `>`  
  
 *oggetto* `<` `.Style>`  
  
 `<` `Style``.../>`  
  
 *oggetto* `</` `.Style>`  
  
 *oggetto* `</` `>`  
  
 L'utilizzo dell'attributo è molto più comune. Uno stile definito inline e non definito nelle risorse è necessariamente limitato all'elemento contenitore e non può essere riutilizzato con facilità perché non dispone di una chiave di risorsa. In generale, uno stile definito dalle risorse è più versatile e utile ed è più coerente con il principio generale del modello di programmazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] della separazione della logica di programma nel codice dalla progettazione nel markup.  
  
 In genere non esiste alcun motivo per impostare uno stile o un modello inline, anche se si intende utilizzare solo lo stile o il modello in tale posizione. La maggior parte degli elementi che possono assumere uno stile o un modello supporta anche una proprietà di contenuto e un modello di contenuto. Se si usa qualsiasi albero logico creato con lo stile o il modello una sola volta, sarebbe ancora più semplice riempire la proprietà di contenuto con gli elementi figlio equivalenti nel markup diretto. In questo modo, il meccanismo dello stile e del modello verrà ignorato.  
  
 Sono inoltre possibili altre sintassi abilitate dalle estensioni di markup che restituiscono un oggetto per gli stili e i modelli. Due estensioni di questo tipo con scenari possibili includono [TemplateBinding](templatebinding-markup-extension.md) e <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
