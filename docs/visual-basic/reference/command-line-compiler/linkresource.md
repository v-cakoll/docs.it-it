---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 0315645eccdc899ac9cf4d0be105297e1fa2a4c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335487"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Crea un collegamento a una risorsa gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

Oppure  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>argomenti  
 `filename`  
 Obbligatorio. The resource file to link to the assembly. If the file name contains a space, enclose the name in quotation marks (" ").  
  
 `identifier`  
 Parametro facoltativo. The logical name for the resource. The name that is used to load the resource. L'impostazione predefinita corrisponde al nome del file. Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`. By default, `filename` is public in the assembly.  
  
## <a name="remarks"></a>Note  
 The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.  
  
 The `-linkresource` option requires one of the `-target` options other than `-target:module`.  
  
 If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace. (For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.  
  
 The file name can be any file format. Può ad esempio risultare opportuno rendere una DLL nativa parte dell'assembly in modo che possa essere installata nella Global Assembly Cache e che sia possibile accedervi dal codice gestito nell'assembly.  
  
 La forma breve di `-linkresource` è `-linkres`.  
  
> [!NOTE]
> The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.  
  
## <a name="example"></a>Esempio  
 The following code compiles `in.vb` and links to resource file `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
