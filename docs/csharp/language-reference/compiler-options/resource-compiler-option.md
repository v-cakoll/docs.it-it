---
title: -resource (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 726956275436e22723bc32b98b2b8b7c7df5fb12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="resource-c-compiler-options"></a>/resource (opzioni del compilatore C#)
Incorpora la risorsa specificata nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 File di risorse .NET Framework da incorporare nel file di output.  
  
 `identifier` (facoltativo)  
 Nome logico della risorsa, usato per caricare la risorsa stessa. L'impostazione predefinita corrisponde al nome del file.  
  
 `accessibility-modifier` (facoltativo)  
 Accessibilità della risorsa: public o private. L'impostazione predefinita è public.  
  
## <a name="remarks"></a>Note  
 Usare [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) per collegare una risorsa a un assembly senza aggiungere il file di risorse al file di output.  
  
 Per impostazione predefinita, le risorse sono pubbliche nell'assembly quando vengono create tramite il compilatore C#. Per renderle private, specificare `private` come modificatore di accessibilità. Non è consentita alcuna accessibilità diversa da `public` o `private`.  
  
 Se `filename` è un file di risorse .NET Framework creato ad esempio da [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri dello spazio dei nomi <xref:System.Resources>. Per altre informazioni, vedere <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Per tutte le altre risorse, usare il `GetManifestResource` metodi di <xref:System.Reflection.Assembly> classe per accedere alla risorsa in fase di esecuzione.  
  
 **/res** rappresenta la versione abbreviata di **/resource**.  
  
 L'ordine delle risorse nel file di output è determinato dall'ordine specificato nella riga di comando.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aggiungere un file di risorse al progetto.  
  
2.  Selezionare il file che si vuole incorporare in **Esplora soluzioni**.  
  
3.  Selezionare **Azione di compilazione** per il file nella finestra **Proprietà**.  
  
4.  Impostare **Azione di compilazione** su **Risorsa incorporata**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e associare il file di risorse `rf.resource`:  
  
```console  
csc /resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
