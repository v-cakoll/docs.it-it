---
title: Stili e modelli inline
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: 9c06f61bce1e17770fa0a9b9ed7a0e20625a79ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545888"
---
# <a name="inline-styles-and-templates"></a>Stili e modelli inline
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce <xref:System.Windows.Style> oggetti e oggetti modello (<xref:System.Windows.FrameworkTemplate> sottoclassi) come un modo per definire l'aspetto visivo di un elemento nelle risorse, in modo che possono essere utilizzati più volte. Per questo motivo, gli attributi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che accettano i tipi <xref:System.Windows.Style> e <xref:System.Windows.FrameworkTemplate> quasi sempre dei riferimenti alle risorse per gli stili e modelli anziché definirne di nuovi inline.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Limitazioni dei modelli e stili in linea  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], proprietà di stile e modello possono essere impostate tecnicamente in uno dei due modi. È possibile utilizzare la sintassi degli attributi per fare riferimento a uno stile definito all'interno di una risorsa, ad esempio `<` *oggetto*`Style="{StaticResource`*myResourceKey*`}" .../>`. In alternativa, è possibile utilizzare la sintassi degli elementi di proprietà per definire uno stile inline, ad esempio:  
  
 `<` *Oggetto* `>`  
  
 `<` *Oggetto* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *Oggetto* `.Style>`  
  
 `</` *Oggetto* `>`  
  
 L'utilizzo dell'attributo è molto più comune. Uno stile che è definita in linea e non definito nelle risorse è necessariamente limitato solo all'elemento contenitore e non possa essere utilizzato nuovamente con la stessa facilità poiché non dispone di alcuna chiave di risorsa. In generale è più versatile e utile uno stile definito dalla risorsa ed è più conforme al [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] principio di modello di separazione logica di programma nel codice dalla progettazione nel markup di programmazione.  
  
 In genere non è necessario impostare uno stile o un modello inline, anche se si intende solo utilizzare tale stile o modello in tale percorso. La maggior parte degli elementi che può richiedere uno stile o modello supportano inoltre una proprietà di contenuto e un modello di contenuto. Se si usa solo l'albero logico creare una sola volta tramite stili o modelli, sarebbe ancora più semplice compilare solo tale proprietà di contenuto con gli elementi figlio equivalente nel markup diretto. In tal modo del tutto i meccanismi di stili e modelli.  
  
 Altri tipi di sintassi abilitate per le estensioni di markup che restituiscono un oggetto sono inoltre disponibili per gli stili e modelli. Due queste estensioni che dispongono di scenari possibili includono [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) e <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
