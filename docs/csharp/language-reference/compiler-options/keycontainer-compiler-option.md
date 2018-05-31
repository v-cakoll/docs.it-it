---
title: -keycontainer (opzioni del compilatore C#)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 5a7b378cad7a1df9249fcbefa28bb9aa9a6a3da4
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472568"
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
 Quando si usa l'opzione **-keycontainer**, il compilatore crea un componente condivisibile. Il compilatore inserisce una chiave pubblica dal contenitore specificato nel manifesto dell'assembly e firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. `sn -i` installa la coppia di chiavi in un contenitore. Questa opzione non è supportata quando il compilatore viene eseguito in CoreCLR. Per firmare un assembly quando si compila in CoreCLR, usare l'opzione [-keyfile](keyfile-compiler-option.md).
  
 Se si esegue la compilazione con [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly quando il modulo verrà compilato in un assembly con [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md). Usare [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) se si vuole aggiungere la chiave pubblica al manifesto dell'assembly, ma si preferisce rimandare la firma dell'assembly a dopo il test di quest'ultimo.  
  
 Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) e [Ritardo della firma di un assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Questa opzione del compilatore non è disponibile nell'ambiente di sviluppo di Visual Studio.  
  
 È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Opzione - keyfile del compilatore C#](keyfile-compiler-option.md) [Opzioni del compilatore C#](index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
