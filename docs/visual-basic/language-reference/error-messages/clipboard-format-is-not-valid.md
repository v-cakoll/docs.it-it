---
title: Formato degli Appunti non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586221"
---
# <a name="clipboard-format-is-not-valid"></a>Formato degli Appunti non valido
Il formato degli Appunti specificato non è compatibile con il metodo in esecuzione. Le cause possibili di questo errore sono:  
  
-   Utilizzando gli Appunti `GetText` o `SetText` metodo con un formato degli Appunti diverso da `vbCFText` o `vbCFLink`.  
  
-   Utilizzando gli Appunti `GetData` o `SetData` metodo con un formato degli Appunti diverso da `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.  
  
-   Utilizzo di `DataObject``GetData` metodo o `SetData` metodo con un formato degli Appunti nell'intervallo riservato da Microsoft Windows ai formati registrati (& HC000 - & HFFFF), quando il formato degli Appunti non è stato registrato con Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere il formato non valido e specificarne uno valido.  
  
## <a name="see-also"></a>Vedere anche  
 [Appunti: aggiunta di altri formati](/cpp/mfc/clipboard-adding-other-formats)
