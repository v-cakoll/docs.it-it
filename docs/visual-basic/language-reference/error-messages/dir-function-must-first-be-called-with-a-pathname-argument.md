---
title: '&#39;Dir&#39; funzione deve essere anzitutto chiamata con un &#39;PathName&#39; argomento'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518488"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39; funzione deve essere anzitutto chiamata con un &#39;PathName&#39; argomento
Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento. La prima chiamata a `Dir` deve includere una `PathName`, ma le chiamate successive a `Dir` non è necessario includere i parametri per recuperare l'elemento successivo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Fornire un `PathName` argomento nella chiamata di funzione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
