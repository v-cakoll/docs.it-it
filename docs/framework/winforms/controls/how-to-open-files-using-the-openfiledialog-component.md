---
title: 'Procedura: aprire file con il componente OpenFileDialog'
ms.date: 02/11/2019
description: Informazioni su come utilizzare il componente OpenFileDialog per aprire la finestra di dialogo Windows per l'esplorazione e la selezione dei file.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904429"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Procedura: aprire file con OpenFileDialog

Il <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente apre la finestra di dialogo di Windows per l'esplorazione e la selezione dei file. Per aprire e leggere i file selezionati, è possibile usare il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> metodo o creare un'istanza della <xref:System.IO.StreamReader?displayProperty=nameWithType> classe. Negli esempi seguenti vengono illustrati entrambi gli approcci.

In .NET Framework per ottenere o impostare la <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà è necessario un livello di privilegio concesso dalla <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Gli esempi eseguono un <xref:System.Security.Permissions.FileIOPermission> controllo delle autorizzazioni e possono generare un'eccezione a causa di privilegi insufficienti se vengono eseguiti in un contesto parzialmente attendibile. Per altre informazioni, vedere [nozioni di base sulla sicurezza dall'accesso di codice](../../misc/code-access-security-basics.md).

È possibile compilare ed eseguire questi esempi come app .NET Framework dalla riga di comando C# o Visual Basic. Per ulteriori informazioni, vedere compilazione dalla [riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

A partire da .NET Core 3,0, è anche possibile compilare ed eseguire gli esempi come app di Windows .NET Core da una cartella che contiene un file di progetto .NET Core Windows Forms * \<folder name> . csproj* .

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Esempio: leggere un file come flusso con StreamReader  
  
Nell'esempio seguente viene usato il <xref:System.Windows.Forms.Button> gestore eventi del controllo Windows Forms <xref:System.Windows.Forms.Control.Click> per aprire <xref:System.Windows.Forms.OpenFileDialog> con il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo. Quando l'utente sceglie un file e seleziona **OK**, un'istanza della <xref:System.IO.StreamReader> classe legge il file e ne Visualizza il contenuto nella casella di testo del modulo. Per ulteriori informazioni sulla lettura da flussi di file, vedere <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> e <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Esempio: aprire un file da una selezione filtrata con OpenFile

Nell'esempio seguente viene usato il <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> gestore eventi del controllo per aprire l'oggetto <xref:System.Windows.Forms.OpenFileDialog> con un filtro che mostra solo file di testo. Quando l'utente sceglie un file di testo e seleziona **OK**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> viene usato il metodo per aprire il file nel blocco note.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](openfiledialog-component-windows-forms.md)
