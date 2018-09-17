---
title: 'Procedura: scrivere testo in file della directory Documenti in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: 894458ad6d69b8bb2836518b90723703733208b6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45617078"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a>Procedura: scrivere testo in file della directory Documenti in Visual Basic
L'oggetto `My.Computer.FileSystem.SpecialDirectories` consente di accedere a directory speciali, ad esempio alla directory **Documenti**.  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a>Per scrivere nuovo testo nei file della directory Documenti  
  
1.  Usare la proprietà `My.Computer.FileSystem.SpecialDirectories.MyDocuments` per specificare il percorso.  
  
     [!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]  
  
2.  Usare il metodo `WriteAllText` per scrivere testo nel file indicato.  
  
     [!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Sostituire `test.txt` con il nome del file in cui si vuole scrivere.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 In questo codice vengono rigenerate tutte le eccezioni che possono verificarsi durante la scrittura di testo nel file. È possibile ridurre la probabilità di eccezioni usando i controlli Windows Form, ad esempio i controlli dei componenti [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) e [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) che limitano le scelte dell'utente a nomi di file validi. L'uso di questi controlli non è comunque infallibile. Il file system può subire variazioni nel tempo che intercorre tra la selezione di un file da parte dell'utente e il momento in cui il codice viene eseguito. Quando si usano i file, è quindi quasi sempre necessaria la gestione delle eccezioni.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi. Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
 In questo esempio viene creato un nuovo file. Per poter creare un file in un'applicazione, è necessario che l'applicazione disponga dell'autorizzazione per la creazione della cartella. Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso. Se il file è già esistente, l'applicazione necessita solo dell'autorizzazione di scrittura, ossia di un privilegio di livello inferiore. Laddove possibile, è più sicuro creare il file durante la fase di distribuzione e concedere privilegi di lettura a un unico file, anziché concedere privilegi per la creazione di una cartella. È anche più sicuro scrivere i dati nelle cartelle utente anziché nella cartella radice o nella cartella **Programmi**. Per altre informazioni, vedere [Panoramica della tecnologia ACL](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
