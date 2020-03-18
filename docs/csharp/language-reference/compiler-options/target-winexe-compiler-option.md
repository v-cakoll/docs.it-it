---
title: -target:winexe (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 981f1b0b6ca9f708bb022a3662ab181a4f472040
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606383"
---
# <a name="-targetwinexe-c-compiler-options"></a>-target:winexe (opzioni del compilatore C#)
Con l'opzione **-target:winexe** il compilatore crea un file eseguibile (EXE), ovvero un programma di Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il file eseguibile verrà creato con estensione .exe. È un programma di Windows che genera un'interfaccia utente dalla libreria di .NET Framework o con le API Windows.  
  
 Usare [-target:exe](./target-exe-compiler-option.md) per creare un'applicazione console.  
  
 Se non diversamente specificato con l'opzione [-out](./out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../programming-guide/main-and-command-args/index.md).  
  
 Se specificato alla riga di comando, tutti i file fino alla successiva opzione **-out** o [-target](./target-compiler-option.md) vengono usati per creare il programma Windows.  
  
 Un solo metodo **Main** è necessario nei file del codice sorgente che vengono compilati in un file con estensione exe. L'opzione [-main](./main-compiler-option.md) consente di specificare la classe che contiene il metodo **Main**, nei casi in cui il codice ha più di una classe con un metodo **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3. Modificare la proprietà **Tipo di output**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` in un programma di Windows:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [-target (opzioni del compilatore C#)](./target-compiler-option.md)
- [Opzioni del compilatore C](./index.md)
