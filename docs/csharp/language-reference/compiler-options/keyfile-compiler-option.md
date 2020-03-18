---
title: -keyfile (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: bf271cc6b6887e930911071d4603b51daed55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970265"
---
# <a name="-keyfile-c-compiler-options"></a>-keyfile (opzioni del compilatore C#)
Specifica il nome file contenente la chiave crittografica.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|----------|----------------|  
|`file`|Nome del file che contiene la chiave con nome sicuro.|  
  
## <a name="remarks"></a>Osservazioni  
 Se si usa questa opzione, il compilatore inserisce la chiave pubblica dal file specificato nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare sn -k `file` nella riga di comando.  
  
 Se si esegue la compilazione con **-target:module**, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](./addmodule-compiler-option.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](./keycontainer-compiler-option.md). Usare [-delaysign](./delaysign-compiler-option.md) se si vuole un assembly con firma parziale.  
  
 Se nella stessa compilazione vengono specificate entrambe le opzioni -keyfile e -keycontainer (tramite opzione della riga di comando o attributo personalizzato), verrà tentato prima il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se invece il compilatore non trova il contenitore di chiavi, effettua un tentativo con il file specificato in -keyfile. Se l'operazione riesce, l'assembly verrà firmato con le informazioni contenute nel file di chiave e le informazioni sulla chiave verranno installate nel contenitore di chiavi (in modo analogo a sn -i) in modo che nella compilazione successiva il contenitore di chiavi sia valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) e [Ritardo della firma di un assembly](../../../standard/assembly/delay-sign.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Firma**.  
  
3. Modificare la proprietà **Scegli un file chiave con nome sicuro**.  
  
 È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
