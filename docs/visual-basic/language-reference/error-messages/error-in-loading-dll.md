---
title: Errore di caricamento della DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 36452cc6ff03042939cd4066aef76129b5bb8f0a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329551"
---
# <a name="error-in-loading-dll-visual-basic"></a>Errore di caricamento della DLL (Visual Basic)
Una libreria di collegamento dinamico (DLL) è una libreria specificata nella clausola `Lib` di un'istruzione `Declare`. Le possibili cause di questo errore includono:  
  
- Il file non è un file eseguibile DLL.  
  
- Il file non è una DLL di Microsoft Windows.  
  
- La DLL fa riferimento a un'altra DLL non presente.  
  
- La DLL o la DLL a cui si fa riferimento non si trova in una directory specificata nel percorso.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se il file è un file di testo di origine e pertanto non un eseguibile DLL, è necessario compilarlo e collegarlo a un modulo eseguibile DLL.  
  
- Se il file non è una DLL di Microsoft Windows, ottenere l'equivalente di Microsoft Windows.  
  
- Se la DLL fa riferimento a un'altra DLL non presente, ottenere la DLL a cui si fa riferimento e renderla disponibile.  
  
- Se la dll o la dll a cui si fa riferimento non è presente in una directory specificata dal percorso, spostare la DLL in una directory a cui si fa riferimento.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
