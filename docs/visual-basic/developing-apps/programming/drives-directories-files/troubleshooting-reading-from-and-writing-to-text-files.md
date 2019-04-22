---
title: 'Risoluzione dei problemi: Lettura e scrittura nei file di testo (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 90a04d9de2ac77c28a92d99e1fe118a1f8ecf448
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831787"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a>Risoluzione dei problemi: Lettura e scrittura nei file di testo (Visual Basic)
In questo argomento vengono descritti i problemi che si riscontrano più comunemente quando si usano i file di testo e vengono suggerite le possibili soluzioni.  
  
## <a name="common-problems"></a>Problemi comuni  
 Alcuni dei problemi più comuni riscontrati quando si lavora con i file di testo sono le eccezioni di sicurezza, le codifiche dei file e i percorsi non validi.  
  
### <a name="security-exceptions"></a>Eccezioni di sicurezza  
 Un'eccezione <xref:System.Security.SecurityException> viene generata quando viene rilevato un errore di sicurezza. Ciò spesso è dovuto al fatto che l'utente non ha le autorizzazioni necessarie, problema che si può risolvere aggiungendo le autorizzazioni o usando i file in uno spazio di memorizzazione isolato.  
  
### <a name="file-encodings"></a>Codifiche dei file  
 Le codifiche dei file, note anche come codifiche dei caratteri, specificano in che modo vengono rappresentati i caratteri durante l'elaborazione del testo. La presenza di caratteri non previsti in un file di testo può causare una codifica non corretta. Per la maggior parte dei file, una codifica può essere preferibile rispetto a un'altra per i caratteri del linguaggio che è o non è in grado di gestire, anche se in genere è preferibile Unicode. Per altre informazioni, vedere [Codifiche dei file](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) e <xref:System.Text.Encoding>.  
  
### <a name="incorrect-paths"></a>Percorsi non corretti  
 Quando si analizzano i percorsi dei file, in particolare i percorsi relativi, è facile inserire i dati errati. Molti problemi possono essere corretti verificando di avere specificato il percorso corretto. Per altre informazioni, vedere [Procedura: Analizzare percorsi di file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [Lettura da file](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Scrittura su file](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [Analisi dei file di testo con l'oggetto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
