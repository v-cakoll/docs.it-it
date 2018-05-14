---
title: -keycontainer (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: edb50dafa376abe55fbeeb312ca5bb8f34c83e7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-keycontainer-c-compiler-options"></a>-keycontainer (opzioni del compilatore C#)
Specifica il nome del contenitore di chiavi crittografiche.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a>Argomenti  
 `string`  
 Nome del contenitore di chiavi con nome sicuro.  
  
## <a name="remarks"></a>Note  
 Quando si usa l'opzione **-keycontainer**, il compilatore crea un componente condivisibile inserendo una chiave pubblica dal contenitore specificato nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata. Per generare un file di chiave, digitare sn -k `file` nella riga di comando. sn -i installa la coppia di chiavi in un contenitore.  
  
 Se si esegue la compilazione con [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly quando il modulo verrà compilato in un assembly con [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md). Usare [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) se si vuole aggiungere la chiave pubblica al manifesto dell'assembly, ma si preferisce rimandare la firma dell'assembly a dopo il test di quest'ultimo.  
  
 Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) e [Ritardo della firma di un assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Questa opzione del compilatore non è disponibile nell'ambiente di sviluppo di Visual Studio.  
  
 È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
