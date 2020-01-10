---
title: Come usare platform invoke per riprodurre un file WAV- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 3ea90f0739ad45c31e4f25836c9de8e708dff2cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75700822"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a>Come usare platform invoke per riprodurre un file WAV (C# guida per programmatori)

Nell'esempio C# di codice seguente viene illustrato come utilizzare i servizi di Platform Invoke per riprodurre un file audio WAV nel sistema operativo Windows.

## <a name="example"></a>Esempio

In questo esempio di codice viene usato <xref:System.Runtime.InteropServices.DllImportAttribute> per importare il punto di ingresso del metodo `winmm.dll` di `PlaySound` come `Form1 PlaySound()`. L'esempio è costituito da un semplice Windows Form con un pulsante. Se si fa clic sul pulsante, viene visualizzata una finestra di dialogo <xref:System.Windows.Forms.OpenFileDialog> standard di Windows che consente di aprire un file da riprodurre. Quando si seleziona un file Wave, questo viene riprodotto utilizzando il metodo `PlaySound()` della libreria *winmm. dll* . Per altre informazioni sul metodo, vedere [Using the PlaySound function with Waveform-Audio Files ](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files) (Uso della funzione PlaySound con file audio Waveform). Cercare e selezionare un file con estensione wav e fare clic su **Apri** per riprodurre il file audio usando platform invoke. Il percorso completo del file selezionato verrà visualizzato in una casella di testo.

La finestra di dialogo **File aperti** viene filtrata in modo da visualizzare solo i file con estensione wav tramite le impostazioni di filtro:

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a>Compilazione del codice

1. Creare un nuovo C# progetto di applicazione Windows Forms in Visual Studio e denominarlo **winsound**.

2. Copiare il codice precedente e incollarlo sul contenuto del file *Form1.cs* .

3. Copiare il codice seguente e incollarlo nel file *Form1.designer.cs* , nel metodo `InitializeComponent()`, dopo qualsiasi codice esistente.

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. Compilare ed eseguire il codice.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Cenni preliminari sull'interoperabilità](interoperability-overview.md)
- [Informazioni dettagliate su platform invoke](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Marshalling dei dati con platform invoke](../../../framework/interop/marshaling-data-with-platform-invoke.md)
