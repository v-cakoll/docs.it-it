---
title: -linkresource ((Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: dee5384696d543442f3280b9fdb535a7d9b6f863
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005495"
---
# <a name="-linkresource-visual-basic"></a>-linkresource ((Visual Basic)
Crea un collegamento a una risorsa gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

oppure  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Obbligatorio. File di risorse da collegare all'assembly. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
 `identifier`  
 facoltativo. Nome logico della risorsa. Nome usato per caricare la risorsa. L'impostazione predefinita corrisponde al nome del file. Facoltativamente, è possibile specificare se il file è pubblico o privato nel manifesto dell'assembly, ad esempio: `-linkres:filename.res,myname.res,public`. Per impostazione predefinita, `filename` è pubblico nell'assembly.  
  
## <a name="remarks"></a>Note  
 L'opzione `-linkresource` non incorpora il file di risorse nel file di output. per eseguire questa operazione, usare l'opzione `-resource`.  
  
 L'opzione `-linkresource` richiede una delle opzioni `-target` diverse da `-target:module`.  
  
 Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi con membri nello spazio dei nomi <xref:System.Resources>. Per altre informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, usare i metodi che iniziano con `GetManifestResource` nella classe <xref:System.Reflection.Assembly>.  
  
 Il nome del file può essere qualsiasi formato di file. Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.  
  
 La forma breve di `-linkresource` è `-linkres`.  
  
> [!NOTE]
> L'opzione `-linkresource` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `in.vb` e i collegamenti al file di risorse `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
