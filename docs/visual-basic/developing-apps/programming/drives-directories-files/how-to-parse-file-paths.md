---
title: 'Procedura: analizzare percorsi di file'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: 6a959994be3a57795dc9f7e3447fa54bf075d3ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335355"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a>Procedura: analizzare percorsi di file in Visual Basic

L'oggetto <xref:Microsoft.VisualBasic.FileIO.FileSystem> offre una serie di metodi utili per l'analisi dei percorsi di file.  
  
- Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> accetta due percorsi e restituisce un percorso combinato correttamente formattato.  
  
- Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> restituisce il percorso assoluto dell'elemento padre del percorso specificato.  
  
- Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> restituisce un oggetto <xref:System.IO.FileInfo> su cui è possibile eseguire query per determinare le proprietà del file, ad esempio il nome e il percorso.  
  
 Non basarsi sull'estensione del nome del file per prendere decisioni in merito al relativo contenuto. È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.  
  
### <a name="to-determine-a-files-name-and-path"></a>Per determinare il nome e il percorso di un file  
  
- Usare le proprietà <xref:System.IO.FileInfo.DirectoryName%2A> e <xref:System.IO.FileInfo.Name%2A> dell'oggetto <xref:System.IO.FileInfo> per determinare il nome e il percorso di un file. In questo esempio il nome e il percorso vengono determinati e quindi visualizzati.  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a>Per combinare il nome e la directory di un file per creare il percorso completo  
  
- Usare il metodo `CombinePath` , specificando la directory e il nome. In questo esempio vengono combinate le stringhe `folderPath` e `fileName` create nell'esempio precedente e viene visualizzato il risultato.  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Vedi anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [Procedura: ottenere la raccolta di file di una directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
