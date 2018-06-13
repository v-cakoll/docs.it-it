---
title: 'Procedura: utilizzare platform invoke per riprodurre un file audio (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: f2234acb9d4eb3b436f3ccdad19525a5ebf26f7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322914"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Procedura: utilizzare platform invoke per riprodurre un file audio (Guida per programmatori C#)
L'esempio di codice C# seguente descrive come usare i servizi platform invoke per riprodurre un file audio con estensione wav nel sistema operativo Windows.  
  
## <a name="example"></a>Esempio  
 In questo esempio di codice viene usato `DllImport` per importare il punto di ingresso del metodo `winmm.dll` di `PlaySound` come `Form1 PlaySound()`. L'esempio è costituito da un semplice Windows Form con un pulsante. Se si fa clic sul pulsante, viene visualizzata una finestra di dialogo <xref:System.Windows.Forms.OpenFileDialog> standard di Windows che consente di aprire un file da riprodurre. Dopo averlo selezionato, il file audio viene riprodotto usando il metodo `PlaySound()` del metodo dell'assembly winmm.DLL. Per altre informazioni sul metodo `PlaySound` di winmm.dll, vedere [Using the PlaySound function with Waveform-Audio Files](https://msdn.microsoft.com/library/aa910379.aspx) (Uso della funzione PlaySound con file audio Waveform). Cercare e selezionare un file con estensione wav e fare clic su **Apri** per riprodurre il file audio usando platform invoke. Il percorso completo del file selezionato verrà visualizzato in una casella di testo.  
  
 La finestra di dialogo **File aperti** viene filtrata in modo da visualizzare solo i file con estensione wav tramite le impostazioni di filtro:  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
### <a name="to-compile-the-code"></a>Per compilare il codice  
  
1.  Creare un nuovo progetto di applicazione Windows C# in Visual Studio e denominarlo **WinSound**.  
  
2.  Copiare il codice precedente e incollarlo nel contenuto del file `Form1.cs`.  
  
3.  Copiare il codice riportato di seguito e incollarlo nel file `Form1.Designer.cs`, nel metodo `InitializeComponent()`, dopo il codice esistente.  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Compilare ed eseguire il codice.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per altre informazioni, vedere [Protezione di .NET Framework](https://technet.microsoft.com/en-us/security/).  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Cenni preliminari sull'interoperabilità](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [Informazioni dettagliate su platform invoke](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
 [Marshalling dei dati con platform invoke](../../../framework/interop/marshaling-data-with-platform-invoke.md)
