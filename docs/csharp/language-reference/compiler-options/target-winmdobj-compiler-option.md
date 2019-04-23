---
title: -target:winmdobj (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 9cc85bf582d737114bc0e621a9568bbb9acb791b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319300"
---
# <a name="-targetwinmdobj-c-compiler-options"></a>-target:winmdobj (opzioni del compilatore C#)
Se si usa l'opzione del compilatore **-target:winmdobj**, viene creato un file intermedio con estensione winmdobj che è possibile convertire in un file binario di Windows Runtime (con estensione winmd). Il file con estensione winmd può quindi essere utilizzato dai programmi C++ e JavaScript, oltre ai programmi di linguaggi gestiti.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a>Osservazioni  
 L'impostazione **winmdobj** segnala al compilatore che è richiesto un modulo intermedio. In risposta, Visual Studio consente di compilare la libreria di classi C# come file con estensione winmdobj. Il file con estensione winmdobj può quindi essere inserito dallo strumento di esportazione <xref:Microsoft.Build.Tasks.WinMDExp> per produrre un file di metadati Windows (winmd). Il file con estensione winmd contiene il codice della libreria originale e i metadati di WinMD utilizzati da JavaScript o C++ e da Windows Runtime.  
  
 L'output di un file compilato usando l'opzione del compilatore **-target:winmdobj** è progettato per essere usato solo come input dell'utilità di esportazione WimMDExp. Al file con estensione winmdobj non viene fatto riferimento direttamente.  
  
 A meno che non si usi l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input. Non è richiesto un metodo [principale](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Se si specifica l'opzione -target:winmdobj al prompt dei comandi, tutti i file fino alla successiva opzione **-out** o [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) vengono usati per creare il programma per Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Per impostare l'opzione del compilatore nell'IDE di Visual Studio per un'applicazione Windows Store  
  
1. In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.  
  
2. Scegliere la scheda **Applicazione**.  
  
3. Nell'elenco **Tipo di output** scegliere **File WinMD**.  
  
     L'opzione **File WinMD** è disponibile solo per i modelli di applicazione [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Esempio  
 Il seguente comando consente di compilare `filename.cs` in un file intermedio con estensione winmdobj.  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
