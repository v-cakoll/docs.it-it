---
title: "Procedura: scrivere all'interno di file binari"
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 72d019f5f49868bd84d0507535e8ebc547b50e25
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334436"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Procedura: scrivere all'interno di file binari in Visual Basic

Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> scrive i dati in un file binario. Se il parametro`append` è `True`, i dati verranno aggiunti al file; in caso contrario i dati nel file saranno sovrascritti.

Se il percorso specificato che esclude il nome file non è valido, verrà generata un'eccezione <xref:System.IO.DirectoryNotFoundException>. Se il percorso sia valido, ma il file non esiste, verrà creato il file.

## <a name="to-write-to-a-binary-file"></a>Per scrivere in un file binario

Usare il metodo `WriteAllBytes` specificando il percorso e nome file e i byte da scrivere. In questo esempio la matrice di dati `CustomerData` viene aggiunta al file denominato `CollectedData.dat`.

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a>Programmazione efficiente

Le condizioni seguenti possono generare un'eccezione:

- Il percorso non è valido per uno di questi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi. (<xref:System.ArgumentException>).

- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).

- `File` punta a un percorso che non esiste (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).

- Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).

- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).

- Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).

- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Procedura: scrivere testo in file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
