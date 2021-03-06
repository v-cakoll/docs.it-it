---
title: 'Procedura: Caricare un file'
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: cee6811d6b6d295c28eb683c5d2f7bcbb5fe94ab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401810"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Procedura: caricare un file in Visual Basic

Il metodo <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> consente di caricare un file e archiviarlo in un percorso remoto. Se il parametro `ShowUI` è impostato su `True`, viene visualizzata una finestra di dialogo che mostra lo stato di avanzamento del processo di caricamento e consente agli utenti di annullare l'operazione.  
  
### <a name="to-upload-a-file"></a>Per caricare un file  
  
- Usare il metodo `UploadFile` per caricare un file, specificando il percorso del file di origine e il percorso della directory di destinazione come stringa o URI (Uniform Resource Identifier). Nell'esempio riportato di seguito il file `Order.txt` viene caricato in `http://www.cohowinery.com/uploads.aspx`.  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a>Per caricare un file e visualizzare lo stato di avanzamento dell'operazione  
  
- Usare il metodo `UploadFile` per caricare un file, specificando il percorso del file di origine e il percorso della directory di destinazione come stringa o URI. Nell'esempio riportato di seguito il file `Order.txt` viene caricato in `http://www.cohowinery.com/uploads.aspx` senza specificare un nome utente o una password, viene visualizzato lo stato di avanzamento del processo di caricamento ed è previsto un intervallo di timeout di 500 millisecondi.  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a>Per caricare un file, specificando un nome utente e una password  
  
- Usare il metodo `UploadFile` per caricare un file, specificando il percorso del file di origine e il percorso della directory di destinazione come stringa o URI e indicando il nome utente e la password. Nell'esempio riportato di seguito il file `Order.txt` viene caricato in `http://www.cohowinery.com/uploads.aspx` specificando il nome utente `anonymous` e una password vuota.  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le condizioni seguenti possono generare un'eccezione:  
  
- Il percorso file locale non è valido (<xref:System.ArgumentException>).  
  
- Autenticazione non riuscita (<xref:System.Security.SecurityException>).  
  
- Timeout della connessione (<xref:System.TimeoutException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [Procedura: Scaricare un file](how-to-download-a-file.md)
- [Procedura: Analizzare percorsi di file](../drives-directories-files/how-to-parse-file-paths.md)
