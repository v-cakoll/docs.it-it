---
title: La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 828c715d9aaceef17d030113e7eda302f025ca9d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282590"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento. La prima chiamata a `Dir` deve includere una `PathName`, ma le chiamate successive a `Dir` non è necessario includere i parametri per recuperare l'elemento successivo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Fornire un `PathName` argomento nella chiamata di funzione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
