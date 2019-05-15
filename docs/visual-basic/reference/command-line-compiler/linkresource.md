---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 637a1d4b7a523feb2fc8da10a0c18e68774c480a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586690"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Crea un collegamento a una risorsa gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Obbligatorio. Il file di risorse da collegare all'assembly. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
 `identifier`  
 Facoltativo. Il nome logico per la risorsa. Il nome usato per caricare la risorsa. L'impostazione predefinita corrisponde al nome del file. Facoltativamente, è possibile specificare se il file è pubblica o privata nel manifesto dell'assembly, ad esempio: `-linkres:filename.res,myname.res,public`. Per impostazione predefinita, `filename` è pubblico nell'assembly.  
  
## <a name="remarks"></a>Note  
 Il `-linkresource` opzione consente di incorporare il file di risorse nel file di output, usare il `-resource` opzione per eseguire questa operazione.  
  
 Il `-linkresource` necessaria un'opzione il `-target` diversa da `-target:module`.  
  
 Se `filename` è un file di risorse .NET Framework creato ad esempio, dal [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri di <xref:System.Resources> dello spazio dei nomi. Per altre informazioni, vedere <xref:System.Resources.ResourceManager>. Per accedere a tutte le altre risorse in fase di esecuzione, usare i metodi che iniziano con `GetManifestResource` nella <xref:System.Reflection.Assembly> classe.  
  
 Il nome del file può avere qualsiasi formato di file. Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.  
  
 La forma breve di `-linkresource` è `-linkres`.  
  
> [!NOTE]
>  Il `-linkresource` opzione non è disponibile dall'ambiente di sviluppo Visual Studio, è disponibile solo quando esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `in.vb` e i collegamenti al file di risorse `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
