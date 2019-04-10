---
title: La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323642"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento. La prima chiamata a `Dir` deve includere una `PathName`, ma le chiamate successive a `Dir` non è necessario includere i parametri per recuperare l'elemento successivo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Fornire un `PathName` argomento nella chiamata di funzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
