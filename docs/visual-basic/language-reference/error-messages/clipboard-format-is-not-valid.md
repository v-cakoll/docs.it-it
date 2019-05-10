---
title: Formato degli Appunti non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 15bc530d1030a8c4d720321ea249fdd7fb6cd8b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623089"
---
# <a name="clipboard-format-is-not-valid"></a>Formato degli Appunti non valido
Il formato degli Appunti specificato non è compatibile con il metodo in esecuzione. Tra le possibili cause di questo errore sono:  
  
- Usando gli Appunti `GetText` oppure `SetText` metodo con un formato degli Appunti diverso da `vbCFText` o `vbCFLink`.  
  
- Usando gli Appunti `GetData` oppure `SetData` metodo con un formato degli Appunti diverso da `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.  
  
- Usando il `GetData` oppure `SetData` metodi di un `DataObject` con un formato degli Appunti nell'intervallo riservato da Microsoft Windows per registrati formati (HC000- & HFFFF), quando il formato degli Appunti non è stato registrato con Microsoft Windows .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere il formato non valido e specificarne uno valido.  
  
## <a name="see-also"></a>Vedere anche

- [Appunti: aggiunta di altri formati](/cpp/mfc/clipboard-adding-other-formats)
