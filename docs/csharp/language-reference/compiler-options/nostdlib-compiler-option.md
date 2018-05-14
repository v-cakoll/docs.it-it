---
title: -nostdlib (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 1dc0ab70ca28626c4a3f505c13ec1d6f828a4b05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (opzioni del compilatore C#)
**-nostdlib** impedisce l'importazione di mscorlib.dll, che definisce l'intero spazio dei nomi di sistema.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Note  
 Usare questa opzione se si vuole definire o creare uno spazio dei nomi e oggetti System personalizzati.  
  
 Se non si specifica **-nostdlib**, mscorlib.dll verrà importata nel programma (equivale a specificare **-nostdlib-**). Specificare **-nostdlib** equivale a specificare **-nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagina **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina di proprietà **Compilazione** .  
  
3.  Fare clic su **Avanzate** .  
  
4.  Modificare la proprietà **Ometti riferimenti a libreria standard (mscorlib.dll)** .  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
