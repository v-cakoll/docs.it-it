---
title: Stili e modelli inline
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091434"
---
# <a name="inline-styles-and-templates"></a>Stili e modelli inline
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce <xref:System.Windows.Style> oggetti e oggetti modello (<xref:System.Windows.FrameworkTemplate> sottoclassi) che consente di definire l'aspetto visivo di un elemento nelle risorse, in modo che possono essere usati più volte. Per questo motivo, gli attributi nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che accettano i tipi <xref:System.Windows.Style> e <xref:System.Windows.FrameworkTemplate> quasi sempre dei riferimenti alle risorse per gli stili esistenti e i modelli anziché definire nuove colonne inline.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Limitazioni dei modelli e stili Inline  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le proprietà di stile e del modello possono essere impostate tecnicamente in uno dei due modi. È possibile usare la sintassi degli attributi per fare riferimento a uno stile che è stato definito all'interno di una risorsa, ad esempio `<` *oggetto*`Style="{StaticResource`*myResourceKey*`}" .../>`. Oppure è possibile usare la sintassi degli elementi per definire uno stile inline, ad esempio:  
  
 `<` *object* `>`  
  
 `<` *object* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *object* `.Style>`  
  
 `</` *object* `>`  
  
 L'utilizzo dell'attributo è molto più comune. Uno stile che viene definito inline e non definito nelle risorse necessariamente ha come ambito solo l'elemento che lo contiene e non possa essere utilizzato nuovamente con la stessa facilità perché non contiene alcuna chiave di risorsa. In genere è più versatile e utile uno stile definito dalla risorsa ed è più in linea generale [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] al principio di separare la logica di programma nel codice di progettazione nel markup del modello di programmazione.  
  
 In genere non è necessario impostare uno stile o modello inline, anche se si intende solo utilizzare tale stile o modello in tale percorso. La maggior parte degli elementi che possono accettare uno stile o modello supportano anche una proprietà di contenuto e un modello di contenuto. Se si usa solo qualsiasi albero logico creare una sola volta tramite stili o modelli, sarebbe ancora più semplice compilare solo tale proprietà di contenuto con gli elementi figlio equivalente nel markup diretta. In tal modo del tutto i meccanismi di stili e modelli.  
  
 Altri tipi di sintassi abilitate per le estensioni di markup che restituiscono un oggetto sono anche possibili per gli stili e modelli. Due tali estensioni con gli scenari possibili includono [TemplateBinding](templatebinding-markup-extension.md) e <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
