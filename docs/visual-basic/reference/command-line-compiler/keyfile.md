---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266742"
---
# <a name="-keyfile"></a>-keyfile
Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 Obbligatorio. File che contiene la chiave. Se il nome del file contiene uno spazio, racchiuderlo tra virgolette (" ").  
  
## <a name="remarks"></a>Osservazioni  
 Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. Per ulteriori informazioni, vedere [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Se si `-target:module`esegue la compilazione con , il nome del file di chiave viene mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.  
  
 È inoltre possibile specificare questa<xref:System.Reflection.AssemblyKeyFileAttribute>opzione come attributo personalizzato ( ) nel codice sorgente per qualsiasi modulo di linguaggio intermedio Microsoft.You can also specify this option as a custom attribute ( ) in the source code for any Microsoft intermediate language module.  
  
 Nel caso `-keyfile` in cui entrambi e [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) vengono specificati (dall'opzione della riga di comando o dall'attributo personalizzato) nella stessa compilazione, il compilatore tenta innanzitutto il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se il compilatore non trova il contenitore `-keyfile`di chiavi, tenta il file specificato con . Se l'operazione riesce, l'assembly viene firmato con le informazioni nel file di `sn -i`chiave e le informazioni sulla chiave vengono installate nel contenitore di chiavi (simile a ) in modo che alla compilazione successiva il contenitore di chiavi sia valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Per ulteriori informazioni sulla firma di un assembly, vedere Creazione e utilizzo di [assembly con nome sicuro.](../../../standard/assembly/create-use-strong-named.md)  
  
> [!NOTE]
> L'opzione `-keyfile` non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Il codice seguente compila `Input.vb` il file di origine e specifica un file di chiave.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../../standard/assembly/index.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
