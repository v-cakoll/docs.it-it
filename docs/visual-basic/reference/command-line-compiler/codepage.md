---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46320937"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`id`|Obbligatorio. Il compilatore Usa la tabella codici specificata dalla `id` per interpretare la codifica dei file di origine.|  
  
## <a name="remarks"></a>Note  
 Per compilare codice sorgente salvato con una codifica specifica, è possibile usare `-codepage` per specificare la tabella codici da usare. Il `-codepage` opzione si applica a tutti i file di codice sorgente nella compilazione. Per altre informazioni, vedere [codifica dei caratteri in .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 Il `-codepage` opzione non è necessaria se i file di codice sorgente sono stati salvati utilizzando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma. Visual Studio Salva tutti i file di codice sorgente con la tabella codici ANSI corrente per impostazione predefinita, a meno che l'utente specifica un'altra codifica nella **Encoding** nella finestra di dialogo. Visual Studio Usa la **Encoding** finestra di dialogo per aprire i file di codice sorgente salvati con una tabella codici diversa.  
  
> [!NOTE]
>  Il `-codepage` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
