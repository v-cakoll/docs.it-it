---
title: 'Procedura: condividere un assembly con altre applicazioni'
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b4c183c3fc0b04121be8bbc2db4027887cbc3132
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644284"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a>Procedura: condividere un assembly con altre applicazioni
Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.  

Per condividere un assembly con altre applicazioni, è necessario che venga inserito nella [global assembly cache (GAC)](gac.md).  
  
Per condividere un assembly:
  
1. Creare l'assembly. Per altre informazioni, vedere [creare assembly](../../standard/assembly/create.md).  
  
2. Assegnare all'assembly un nome sicuro. Per altre informazioni, vedere [procedura: firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md).  
  
3. Assegnare all'assembly le informazioni sulla versione. Per ulteriori informazioni, vedere [controllo delle versioni degli assembly](../../standard/assembly/versioning.md).  
  
4. Aggiungere l'assembly al Global Assembly Cache. Per altre informazioni, vedere [procedura: installare un assembly nel Global assembly cache](install-assembly-into-gac.md).  
  
5. Accedere ai tipi contenuti nell'assembly da altre applicazioni. Per altre informazioni, vedere [procedura: fare riferimento a un assembly con nome sicuro](../../standard/assembly/reference-strong-named.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../api/index.md)
- [Concetti di programmazione (Visual Basic)](../../../api/index.md)
- [Programmare con gli assembly](../../standard/assembly/index.md)
