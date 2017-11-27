---
title: '&#39; Dir &#39; funzione deve essere anzitutto chiamata con un &#39; Percorso &#39; argomento'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 843918fe9cb0b9dece076b5dc1373c3571588caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39; Dir &#39; funzione deve essere anzitutto chiamata con un &#39; Percorso &#39; argomento
Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento. La prima chiamata a `Dir` deve includere un `PathName`, ma le chiamate successive a `Dir` non è necessario includere parametri per recuperare l'elemento successivo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Fornire un `PathName` argomento nella chiamata di funzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
