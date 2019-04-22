---
title: Formato degli Appunti non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817178"
---
# <a name="clipboard-format-is-not-valid"></a>Formato degli Appunti non valido
Il formato degli Appunti specificato non è compatibile con il metodo in esecuzione. Tra le possibili cause di questo errore sono:  
  
-   Usando gli Appunti `GetText` oppure `SetText` metodo con un formato degli Appunti diverso da `vbCFText` o `vbCFLink`.  
  
-   Usando gli Appunti `GetData` oppure `SetData` metodo con un formato degli Appunti diverso da `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.  
  
-   Usando il `GetData` oppure `SetData` metodi di un `DataObject` con un formato degli Appunti nell'intervallo riservato da Microsoft Windows per registrati formati (HC000- & HFFFF), quando il formato degli Appunti non è stato registrato con Microsoft Windows .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere il formato non valido e specificarne uno valido.  
  
## <a name="see-also"></a>Vedere anche

- [Appunti: Aggiunta di altri formati](/cpp/mfc/clipboard-adding-other-formats)
