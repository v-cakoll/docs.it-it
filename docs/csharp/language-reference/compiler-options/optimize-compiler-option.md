---
title: -optimize (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: bec99ca582070a99fd8b734ef8a7b9e71d945488
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606607"
---
# <a name="-optimize-c-compiler-options"></a>-optimize (opzioni del compilatore C#)
L'opzione **-optimize** abilita o disabilita le ottimizzazioni eseguite dal compilatore per ridurre le dimensioni del file di output e aumentarne la velocità e l'efficienza.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a>Osservazioni  
 **-optimize** comunica poi a Common Language Runtime di ottimizzare il codice in fase di esecuzione.  
  
 Per impostazione predefinita, le ottimizzazioni sono disabilitate. Per abilitarle, specificare **-optimize+**.  
  
 Durante la compilazione di un modulo per l'uso da parte di un assembly, specificare per **-optimize** le stesse impostazioni usate per l'assembly.  
  
 **-o** è la versione abbreviata di **-optimize**.  
  
 Le opzioni **-optimize** e [-debug](./debug-compiler-option.md) possono essere usate in modo combinato.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Modificare la proprietà **Ottimizza codice**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `t2.cs` e abilitare le ottimizzazioni del compilatore:  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
