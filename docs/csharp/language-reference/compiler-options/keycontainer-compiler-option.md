---
title: -keycontainer (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
dev_langs:
- CSharp
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5d27fa0b80ca6df15394ad1fda149377cac41a8b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="keycontainer-c-compiler-options"></a>/keycontainer (opzioni del compilatore C#)
Specifica il nome del contenitore di chiavi crittografiche.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/keycontainer:string  
```  
  
## <a name="arguments"></a>Argomenti  
 `string`  
 Nome del contenitore di chiavi con nome sicuro.  
  
## <a name="remarks"></a>Note  
 Quando viene usata l'opzione **/keycontainer**, il compilatore crea un componente condivisibile inserendo una chiave pubblica dal contenitore specificato nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata. Per generare un file di chiave, digitare sn -k `file` nella riga di comando. sn -i installa la coppia di chiavi in un contenitore.  
  
 Se si esegue la compilazione con [/target: module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly quando il modulo verrà compilato in un assembly con [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md). Usare [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) se si vuole aggiungere la chiave pubblica al manifesto dell'assembly, ma si preferisce rimandare la firma dell'assembly a dopo il test di questo.  
  
 Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](https://msdn.microsoft.com/library/xwb8f617) e [Ritardo della firma di un assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Questa opzione del compilatore non è disponibile nell'ambiente di sviluppo di Visual Studio.  
  
 È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

