---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: a498ec6f79c68ca924525fe837f356f097b01fd1
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746030"
---
# <a name="-keyfile"></a>-keyfile
Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 Obbligatorio. File che contiene la chiave. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
## <a name="remarks"></a>Note  
 Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Se esegue la compilazione con `-target:module`, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly che viene creato quando si compila un assembly con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.  
  
 È possibile specificare questa opzione anche come attributo personalizzato (<xref:System.Reflection.AssemblyKeyFileAttribute>) nel codice sorgente di qualsiasi modulo di Microsoft intermediate language.  
  
 In entrambi casi `-keyfile` e [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) vengono specificati (tramite opzione della riga di comando o attributo personalizzato) nella stessa compilazione, il compilatore cerca prima il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se il compilatore non trova il contenitore di chiavi, prova con il file specificato `-keyfile`. Se l'esito è positivo, l'assembly è firmato con le informazioni nel file di chiave e le informazioni sulla chiave è installati nel contenitore di chiavi (simile a `sn -i`) in modo che nella compilazione successiva il contenitore di chiavi saranno valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Visualizzare [creazione e assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) per altre informazioni su come firmare un assembly.  
  
> [!NOTE]
>  Il `-keyfile` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente consente di compilare file sorgente `Input.vb` e specifica un file di chiave.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Vedere anche
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-riferimenti (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
