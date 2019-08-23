---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: b2084a1c0ee30478cdc9193cdfcb19476499ee93
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924876"
---
# <a name="-keyfile"></a>-keyfile
Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 Richiesto. File contenente la chiave. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
## <a name="remarks"></a>Note  
 Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. Per ulteriori informazioni, vedere [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Se si esegue la `-target:module`compilazione con, il nome del file di chiave viene mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.  
  
 È possibile specificare questa opzione anche come attributo personalizzato (<xref:System.Reflection.AssemblyKeyFileAttribute>) nel codice sorgente di qualsiasi modulo Microsoft Intermediate Language.  
  
 Se nella stessa `-keyfile` compilazione vengono specificati sia che [-](../../../visual-basic/reference/command-line-compiler/keycontainer.md) key container (per opzione della riga di comando o attributo personalizzato), il compilatore tenta prima di tutto il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se il compilatore non trova il contenitore di chiavi, tenta il file specificato con `-keyfile`. Se l'operazione ha esito positivo, l'assembly viene firmato con le informazioni contenute nel file di chiave e le informazioni sulla chiave vengono installate nel contenitore di `sn -i`chiavi (simile a) in modo che nella compilazione successiva il contenitore di chiavi sarà valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) .  
  
> [!NOTE]
> L' `-keyfile` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila il file `Input.vb` di origine e specifica un file di chiave.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../../standard/assembly/index.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
