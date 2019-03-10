---
title: 'Procedura: Aprire i file con il componente OpenFileDialog'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 5781543a61d77ef8f0658e95759c57fdb77cfc4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723088"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Procedura: File aperti con OpenFileDialog 

Il <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente consente di aprire la finestra di dialogo di Windows per l'esplorazione e selezione dei file. Per aprire e leggere i file selezionati, è possibile usare la <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> metodo, o creare un'istanza del <xref:System.IO.StreamReader?displayProperty=nameWithType> classe. Gli esempi seguenti illustrano entrambi gli approcci. 

In .NET Framework, per ottenere o impostare il <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà richiede un livello di privilegio concesso dal <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Gli esempi eseguono un <xref:System.Security.Permissions.FileIOPermission> autorizzazione controllare e può generare un'eccezione a causa di privilegi sufficienti, se eseguito in un contesto parzialmente attendibile. Per altre informazioni, vedere [nozioni fondamentali sulla sicurezza di accesso di codice](../../misc/code-access-security-basics.md).

È possibile compilare ed eseguire questi esempi di come le app .NET Framework dal C# o riga di comando di Visual Basic. Per altre informazioni, vedere [della riga di comando edificio con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oppure [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

A partire da .NET Core 3.0, è possibile anche creare ed eseguire gli esempi come le app .NET Core di Windows da una cartella che dispone di un form di Windows di .NET Core  *\<nome cartella > csproj* file di progetto. 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Esempio: Leggere un file come flusso con StreamReader  
  
L'esempio seguente usa i moduli di Windows <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore dell'evento per aprire il <xref:System.Windows.Forms.OpenFileDialog> con il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo). Dopo che l'utente sceglie un file e seleziona **OK**, un'istanza di <xref:System.IO.StreamReader> legge il file di classe e ne visualizza il contenuto nella casella di testo del form. Per altre informazioni sulla lettura da flussi di file, vedere <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> e <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Esempio: Aprire un file da una selezione con OpenFile filtrata 

L'esempio seguente usa il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore dell'evento per aprire la <xref:System.Windows.Forms.OpenFileDialog> con un filtro che mostra solo i file di testo. Dopo che l'utente sceglie un file di testo e seleziona **OK**, il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> metodo viene utilizzato per aprire il file nel blocco note.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](openfiledialog-component-windows-forms.md)
