---
title: 'Procedura: recuperare il contenuto della directory Documenti'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: cf4470020507c581999b9d72602ddb6e3e76ed74
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74334540"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Procedura: recuperare il contenuto della directory Documenti in Visual Basic

L'oggetto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> può essere usato per leggere il contenuto di molte delle directory di **Tutti gli utenti**, ad esempio **Documenti** o **Desktop**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Per leggere il contenuto dalla cartella Documenti  
  
- Usare il metodo `ReadAllText` per leggere il testo di ogni file in una directory specifica. Il codice seguente consente di specificare una directory e un file e di usare `ReadAllText` per leggere il contenuto nella stringa denominata `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
