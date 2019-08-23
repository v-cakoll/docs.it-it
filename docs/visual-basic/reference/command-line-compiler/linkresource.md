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
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924866"
---
# <a name="-linkresource-visual-basic"></a>-linkresource ((Visual Basic)
Crea un collegamento a una risorsa gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Richiesto. File di risorse da collegare all'assembly. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
 `identifier`  
 facoltativo. Nome logico della risorsa. Nome usato per caricare la risorsa. L'impostazione predefinita corrisponde al nome del file. Facoltativamente, è possibile specificare se il file è pubblico o privato nel manifesto dell'assembly, ad esempio: `-linkres:filename.res,myname.res,public`. Per impostazione predefinita `filename` , è Public nell'assembly.  
  
## <a name="remarks"></a>Note  
 L' `-linkresource` opzione non incorpora il file di risorse nel file di output. utilizzare l' `-resource` opzione per eseguire questa operazione.  
  
 L' `-linkresource` opzione richiede una `-target` delle opzioni diverse da `-target:module`.  
  
 Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi <xref:System.Resources> con i membri nello spazio dei nomi. Per altre informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, usare i metodi `GetManifestResource` che iniziano <xref:System.Reflection.Assembly> con nella classe.  
  
 Il nome del file può essere qualsiasi formato di file. Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.  
  
 La forma breve di `-linkresource` è `-linkres`.  
  
> [!NOTE]
> L' `-linkresource` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `in.vb` e collega a un file `rf.resource`di risorse.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
