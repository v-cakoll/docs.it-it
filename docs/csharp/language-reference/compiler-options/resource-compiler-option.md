---
title: -resource (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: e14bf59f5922a918b627af22c052c8efd9081e84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602520"
---
# <a name="-resource-c-compiler-options"></a>-resource (opzioni del compilatore C#)
Incorpora la risorsa specificata nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 File di risorse .NET Framework da incorporare nel file di output.  
  
 `identifier` (facoltativo)  
 Nome logico della risorsa, usato per caricare la risorsa stessa. L'impostazione predefinita corrisponde al nome del file.  
  
 `accessibility-modifier` (facoltativo)  
 Accessibilità della risorsa: public o private. Il valore predefinito è public.  
  
## <a name="remarks"></a>Osservazioni  
 Usare [-linkresource](./linkresource-compiler-option.md) per collegare una risorsa a un assembly senza aggiungere il file di risorse al file di output.  
  
 Per impostazione predefinita, le risorse sono pubbliche nell'assembly quando vengono create tramite il compilatore C#. Per renderle private, specificare `private` come modificatore di accessibilità. Non è consentita alcuna accessibilità diversa da `public` o `private`.  
  
 Se `filename` è un file di risorse .NET Framework creato ad esempio da [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri dello spazio dei nomi <xref:System.Resources>. Per altre informazioni, vedere <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Per tutte le altre risorse, per accedere alla risorsa in fase di esecuzione usare i metodi `GetManifestResource` della classe <xref:System.Reflection.Assembly>.  
  
 **-res** rappresenta la versione abbreviata di **-resource**.  
  
 L'ordine delle risorse nel file di output è determinato dall'ordine specificato nella riga di comando.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aggiungere un file di risorse al progetto.  
  
2. Selezionare il file che si vuole incorporare in **Esplora soluzioni**.  
  
3. Selezionare **Azione di compilazione** per il file nella finestra **Proprietà**.  
  
4. Impostare **Azione di compilazione** su **Risorsa incorporata**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e associare il file di risorse `rf.resource`:  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
