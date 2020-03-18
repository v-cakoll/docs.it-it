---
title: -linkresource (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 41af8e0ba8ffebd07d3cb1d2bc5fbc04b8cd595d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173731"
---
# <a name="-linkresource-c-compiler-options"></a>-linkresource (opzioni del compilatore C#)
Crea un collegamento a una risorsa di .NET Framework nel file di output. Il file di risorse non viene aggiunto al file di output. Questa opzione è diversa dall'opzione [-resource](./resource-compiler-option.md), che invece incorpora un file di risorse nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 File di risorse .NET Framework a cui si vuole stabilire un collegamento dall'assembly.  
  
 `identifier` (facoltativo)  
 Nome logico della risorsa, usato per caricare la risorsa stessa. L'impostazione predefinita corrisponde al nome del file.  
  
 `accessibility-modifier` (facoltativo)  
 Accessibilità della risorsa: public o private. Il valore predefinito è public.  
  
## <a name="remarks"></a>Osservazioni  
 Per impostazione predefinita, le risorse collegate sono pubbliche nell'assembly quando vengono create con il compilatore C#. Per renderle private, specificare `private` come modificatore di accessibilità. Non è consentito alcun modificatore diverso da `public` o `private`.  
  
 Per **-linkresource** è necessaria un'opzione [-target](./target-compiler-option.md) diversa da **-target:module**.  
  
 Se `filename` è un file di risorse .NET Framework creato ad esempio da [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri dello spazio dei nomi <xref:System.Resources>. Per altre informazioni, vedere <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Per tutte le altre risorse, per accedere alla risorsa in fase di esecuzione usare i metodi `GetManifestResource` della classe <xref:System.Reflection.Assembly>.  
  
 Il file specificato in `filename` può avere qualsiasi formato. Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly. Nel secondo degli esempi seguenti viene illustrato come effettuare questa operazione. È possibile eseguire la stessa operazione in Assembly Linker. Nel terzo degli esempi seguenti viene illustrato come effettuare questa operazione. Per altre informazioni, vedere [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) e [Uso di assembly e della Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).  
  
 **-linkres** rappresenta la versione abbreviata di **-linkresource**.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` e stabilire il collegamento al file di risorse `rf.resource`:  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a>Esempio  
 Compilare `A.cs` in una DLL, creare un collegamento a una DLL N.dll nativa e inserire l'output nella Global Assembly Cache. In questo esempio i file A.dll e N.dll verranno memorizzati entrambi nella Global Assembly Cache.  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene eseguita la stessa operazione descritta in precedenza, ma vengono usate le opzioni di Assembly Linker.  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md)
- [Uso di assembly e della Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
