---
title: -target:exe (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: b9efa25870e11e0140cba2ad39c3bc4515056ce3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697881"
---
# <a name="-targetexe-c-compiler-options"></a>-target:exe (opzioni del compilatore C#)
L'opzione **-target:exe** indica al compilatore di creare un file eseguibile (EXE), applicazione console.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a>Note  
 L'opzione **-target:exe** è attiva per impostazione predefinita. Il file eseguibile verrà creato con estensione .exe.  
  
 Usare [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) per creare l'eseguibile di un programma Windows.  
  
 Se non diversamente specificato con l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Se specificato dalla riga di comando, tutti i file fino alla successiva opzione **-out** o **-target:module** vengono usati per creare il file con estensione .exe  
  
 Un solo metodo **Main** è necessario nei file del codice sorgente che vengono compilati in un file con estensione exe. L'opzione del compilatore [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) consente di specificare la classe che contiene il metodo **Main**, nei casi in cui il codice ha più di una classe con un metodo **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagine **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3.  Modificare la proprietà **Tipo di output**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Esempio  
 Ciascuna delle righe di comando seguenti compilerà `in.cs`, creando `in.exe`:  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
