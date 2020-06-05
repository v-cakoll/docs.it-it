---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 34dbf36cc79a8c4715cf6a07c57d559e14f40030
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363630"
---
# <a name="-codepage-visual-basic"></a>-tabella codici (Visual Basic)
Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`id`|Obbligatorio. Il compilatore usa la tabella codici specificata da `id` per interpretare la codifica dei file di origine.|  
  
## <a name="remarks"></a>Commenti  
 Per compilare il codice sorgente salvato con una codifica specifica, è possibile usare `-codepage` per specificare la tabella codici da usare. L' `-codepage` opzione si applica a tutti i file del codice sorgente nella compilazione. Per ulteriori informazioni, vedere [codifica dei caratteri nella .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 L' `-codepage` opzione non è necessaria se i file del codice sorgente sono stati salvati usando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma. Per impostazione predefinita, Visual Studio Salva tutti i file del codice sorgente con la tabella codici ANSI corrente, a meno che l'utente non specifichi un'altra codifica nella finestra di dialogo **codifica** . Visual Studio usa la finestra di dialogo **codifica** per aprire i file di codice sorgente salvati con una tabella codici diversa.  
  
> [!NOTE]
> L' `-codepage` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
