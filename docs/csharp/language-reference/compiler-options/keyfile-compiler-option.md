---
title: -keyfile (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d120b325f433108cd1b01dd1c25d2a0e55da401b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="keyfile-c-compiler-options"></a>/keyfile (opzioni del compilatore C#)
Specifica il nome file contenente la chiave crittografica.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|----------|----------------|  
|`file`|Nome del file che contiene la chiave con nome sicuro.|  
  
## <a name="remarks"></a>Note  
 Se si usa questa opzione, il compilatore inserisce la chiave pubblica dal file specificato nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata. Per generare un file di chiave, digitare sn -k `file` nella riga di comando.  
  
 Se si esegue la compilazione con **/target: module**, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md). Usare [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) se si vuole che l'assembly abbia una firma parziale.  
  
 Se nella stessa compilazione vengono specificate sia /keyfile che /keycontainer (tramite opzione della riga di comando o attributo personalizzato), verrà tentato prima il contenitore di chiavi. Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi. Se invece il compilatore non trova il contenitore di chiavi, effettua un tentativo con il file specificato in /keyfile. Se l'operazione riesce, l'assembly verrà firmato con le informazioni contenute nel file di chiave e le informazioni sulla chiave verranno installate nel contenitore di chiavi (in modo analogo a sn -i) in modo che nella compilazione successiva il contenitore di chiavi sia valido.  
  
 Si noti che un file di chiave può contenere solo la chiave pubblica.  
  
 Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) e [Ritardo della firma di un assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagina **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina della proprietà **Firma**.  
  
3.  Modificare la proprietà **Scegli un file chiave con nome sicuro**.  
  
 È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
