---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0be7d230f16750395aaceb3c94539546716b8fd
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="keyfile"></a>/keyfile
Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 Obbligatorio. File che contiene la chiave. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
## <a name="remarks"></a>Note  
 Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e l'assembly finale verrà firmato con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. Per ulteriori informazioni, vedere [Sn.exe (strumento nome sicuro)][Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Se si compila con `/target:module`, il nome del file di chiave verrà conservato nel modulo e incorporato nell'assembly che viene creato quando si compila un assembly con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Usare [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole che l'assembly abbia una firma parziale.  
  
 È possibile specificare questa opzione anche come attributo personalizzato (<xref:System.Reflection.AssemblyKeyFileAttribute>) nel codice sorgente di qualsiasi modulo di Microsoft intermediate language.  
  
 In caso `/keyfile` e [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) vengono specificati (tramite opzione della riga di comando o un attributo personalizzato) nella stessa compilazione, il compilatore tenta innanzitutto il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se il compilatore non trova il contenitore di chiavi, prova nuovamente con il file specificato con `/keyfile`. Se l'esito è positivo, l'assembly è firmato con le informazioni nel file di chiave e le informazioni sulla chiave è installati nel contenitore di chiavi (simile a `sn -i`) in modo che alla successiva compilazione, il contenitore di chiavi valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Vedere [creazione e uso degli assembly](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) per ulteriori informazioni su come firmare un assembly.  
  
> [!NOTE]
>  Il `/keyfile` opzione non è disponibile all'interno di [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] ambiente di sviluppo; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila i file di origine `Input.vb` e specifica un file di chiave.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
