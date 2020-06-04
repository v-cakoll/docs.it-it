---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 3f476f6b6db1a788002a938eb5ae4bbbed7a5dae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408575"
---
# <a name="-keyfile"></a>-keyfile
Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 Obbligatorio. File contenente la chiave. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").  
  
## <a name="remarks"></a>Commenti  
 Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. Per ulteriori informazioni, vedere [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Se si esegue la compilazione con `-target:module` , il nome del file di chiave viene mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](addmodule.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](keycontainer.md). Usare [-delaysign](delaysign.md) se si vuole un assembly con firma parziale.  
  
 È possibile specificare questa opzione anche come attributo personalizzato ( <xref:System.Reflection.AssemblyKeyFileAttribute> ) nel codice sorgente di qualsiasi modulo Microsoft Intermediate Language.  
  
 Se `-keyfile` nella stessa compilazione vengono specificati sia che [-key container](keycontainer.md) (per opzione della riga di comando o attributo personalizzato), il compilatore tenta prima di tutto il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se il compilatore non trova il contenitore di chiavi, tenta il file specificato con `-keyfile` . Se l'operazione ha esito positivo, l'assembly viene firmato con le informazioni contenute nel file di chiave e le informazioni sulla chiave vengono installate nel contenitore di chiavi (simile a `sn -i` ) in modo che nella compilazione successiva il contenitore di chiavi sarà valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) .  
  
> [!NOTE]
> L' `-keyfile` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Il codice seguente compila il file `Input.vb` di origine e specifica un file di chiave.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../../standard/assembly/index.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [-Reference (Visual Basic)](reference.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
