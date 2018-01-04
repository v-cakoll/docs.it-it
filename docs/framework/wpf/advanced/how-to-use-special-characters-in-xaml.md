---
title: 'Procedura: Usare caratteri speciali in XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79df87d716224cb8681c1688d94fe56077452c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-special-characters-in-xaml"></a>Procedura: Usare caratteri speciali in XAML
File di markup che vengono creati in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] vengono salvate automaticamente nel [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato di file UTF-8, il che significa che i caratteri speciali, ad esempio accenti, vengono codificati correttamente. Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente. Seguono questi caratteri speciali di [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard per la codifica.  
  
 La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:  
  
|Carattere|Sintassi|Descrizione|  
|---------------|------------|-----------------|  
|<|`<`|Simbolo minore di.|  
|>|`>`|Simbolo maggiore di.|  
|&|`&`|Simbolo e commerciale.|  
|"|`"`|Simbolo virgoletta doppia.|  
  
> [!NOTE]
>  Se si crea un file di markup mediante un testo dell'editor, ad esempio [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] blocco note, è necessario salvare il file di [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] il formato di file UTF-8 per mantenere qualsiasi codifica i caratteri speciali.  
  
 L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
