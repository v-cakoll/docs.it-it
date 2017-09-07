---
title: -resource (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /resource
dev_langs:
- CSharp
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: 16
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
ms.openlocfilehash: fdb7be630300e11c2e63d88bd6add7d229714bfa
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

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
  
 Se `filename` è un file di risorse .NET Framework creato ad esempio da [Resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri dello spazio dei nomi <xref:System.Resources>. Per altre informazioni, vedere <xref:System.Resources.ResourceManager?displayProperty=fullName>. Per tutte le altre risorse, usare i metodi `GetManifestResource`* della classe <xref:System.Reflection.Assembly> per accedere alla risorsa in fase di runtime.  
  
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
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

