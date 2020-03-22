---
title: 'Procedura: scaricare file'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: 4923feb46ff638de9514a4d70fc00367491a6f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345626"
---
# <a name="how-to-download-a-file-in-visual-basic"></a>Procedura: scaricare file in Visual Basic

Il metodo <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> può essere usato per scaricare un file remoto e archiviarlo in un percorso specifico. Se il parametro `ShowUI` è impostato su `True`, viene visualizzata una finestra che mostra lo stato di avanzamento del download e consente agli utenti di annullare l'operazione. Per impostazione predefinita non vengono sovrascritti i file esistenti con lo stesso nome. Se si desidera sovrascrivere i file esistenti, impostare il parametro `overwrite` su `True`.

Le seguenti condizioni possono generare un'eccezione:

- Il nome dell'unità non è valido (<xref:System.ArgumentException>).

- L'autenticazione necessaria non è stata fornita (<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>).

- Il server non risponde entro il `connectionTimeout` (<xref:System.TimeoutException>) specificato.

- La richiesta è stata rifiutata dal sito Web (<xref:System.Net.WebException>).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto. È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic. Prima di usare i dati nell'applicazione verificare tutti gli input. È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.

### <a name="to-download-a-file"></a>Per scaricare un file

- Usare il metodo `DownloadFile` per scaricare il file, specificando il percorso del file di destinazione come stringa o URI e specificando la posizione in cui archiviare il file. Questo esempio scarica il file `WineList.txt` da `http://www.cohowinery.com/downloads` e lo salva in `C:\Documents and Settings\All Users\Documents`:

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Per scaricare un file, specificando un intervallo di timeout

- Usare il metodo `DownloadFile` per scaricare il file, specificando il percorso del file di destinazione come stringa o URI che specifica la posizione in cui archiviare il file e specificando l'intervallo di timeout in millisecondi (il valore predefinito è 1000). Questo esempio scarica il file `WineList.txt` da `http://www.cohowinery.com/downloads` e lo salva in `C:\Documents and Settings\All Users\Documents`, specificando un intervallo di timeout di 500 millisecondi:

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Per scaricare un file, fornendo un nome utente e una password

- Usare il metodo `DownLoadFile` per scaricare il file, specificando il percorso del file di destinazione come stringa o URI e specificando la posizione in cui archiviare il file, il nome utente e la password. Questo esempio scarica il file `WineList.txt` da `http://www.cohowinery.com/downloads` e lo salva in `C:\Documents and Settings\All Users\Documents`, con il nome utente `anonymous` e una password vuota.

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > Il protocollo FTP utilizzato dal metodo `DownLoadFile` invia informazioni, comprese le password, in testo normale e non deve essere usato per trasmettere informazioni riservate.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [Procedura: caricare un fileHow to: Upload a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)
- [Procedura: analizzare percorsi di file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
