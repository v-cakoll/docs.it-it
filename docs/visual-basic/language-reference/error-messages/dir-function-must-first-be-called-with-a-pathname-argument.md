---
title: La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1a5d6ed145199ae995a98b6c1180fa3aedf9942c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834158"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento. La prima chiamata a `Dir` deve includere una `PathName`, ma le chiamate successive a `Dir` non è necessario includere i parametri per recuperare l'elemento successivo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Fornire un `PathName` argomento nella chiamata di funzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
