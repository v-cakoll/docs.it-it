---
title: -win32icon (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: f3df92d8d0b0135eac1a055afafffa0015fecc2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606271"
---
# <a name="-win32icon-c-compiler-options"></a>-win32icon (opzioni del compilatore C#)
Con l'opzione **-win32icon** viene inserito un file con estensione ico nel file di output, che assume l'aspetto desiderato in Esplora file.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Il file con estensione ico da aggiungere al file di output.  
  
## <a name="remarks"></a>Osservazioni  
 Un file con estensione ico può essere creato mediante il [compilatore di risorse](/windows/desktop/menurc/resource-compiler). Il Compilatore di risorse viene richiamato quando si compila un programma Visual C++. Dal file .rc viene creato un file .ico.  
  
 Vedere [-linkresource](./linkresource-compiler-option.md) (per fare riferimento a un file di risorse di .NET Framework) o a [-resource](./resource-compiler-option.md) (per associarlo). Vedere [-win32res](./win32res-compiler-option.md) per importare un file con estensione res.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3. Modificare la proprietà **Icona dell'applicazione**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e associare un file con estensione ico `rf.ico` per produrre `in.exe`:  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
