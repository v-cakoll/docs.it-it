---
title: Lunghezza del record non valida
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 747d62cb41ef841b4486e0c7108c37a86929683e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bad-record-length"></a>Lunghezza del record non valida
Di seguito sono riportate le cause possibili dell'errore:  
  
-   La lunghezza di una variabile del record specificata un `FileGet`, `FileGetObject`, `FilePut` o `FilePutObject` istruzione è diversa da quella specificata nel corrispondente `FileOpen` istruzione.  
  
-   La variabile in un `FilePut` o `FilePutObject` o istruzione include una stringa di lunghezza variabile.  
  
-   La variabile in un `FilePut` o `FilePutObject` è o include un `Variant` tipo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che la somma delle dimensioni delle variabili di lunghezza fissa di tipo definito dall'utente che definisce il record del tipo di variabile è uguale al valore indicato nel `FileOpen` dell'istruzione `Len` clausola.  
  
2.  Se la variabile in un `FilePut` o `FilePutObject` o istruzione include una stringa di lunghezza variabile, assicurarsi che la stringa di lunghezza variabile sia inferiore alla lunghezza di record specificata nel almeno 2 caratteri di `Len` clausola del `FileOpen` istruzione.  
  
3.  Se la variabile in un `FilePut` o `FilePutObject` è o include un `Variant` assicurarsi che la stringa a lunghezza variabile è inferiore alla lunghezza del record specificata almeno 4 byte il `Len` clausola del `FileOpen` istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
