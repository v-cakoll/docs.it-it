---
title: 'Procedura: Condividere un assembly con altre applicazioni'
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b1ef195458dd2de95eeb5e25089339e55d9e3fbb
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972949"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a>Procedura: Condividere un assembly con altre applicazioni
Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.  

Per condividere un assembly con altre applicazioni, è necessario che venga inserito nella [global assembly cache (GAC)](gac.md).  
  
Per condividere un assembly:
  
1. Creare l'assembly. Per altre informazioni, vedere [creare assembly](../../standard/assembly/create.md).  
  
2. Assegnare all'assembly un nome sicuro. Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md).  
  
3. Assegnare all'assembly le informazioni sulla versione. Per ulteriori informazioni, vedere [controllo delle versioni degli assembly](../../standard/assembly/versioning.md).  
  
4. Aggiungere l'assembly al Global Assembly Cache. Per altre informazioni, vedere [Procedura: Installare un assembly nel Global Assembly Cache](install-assembly-into-gac.md).  
  
5. Accedere ai tipi contenuti nell'assembly da altre applicazioni. Per altre informazioni, vedere [Procedura: Fare riferimento a un assembly](../../standard/assembly/reference-strong-named.md)con nome sicuro.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../api/index.md)
- [Concetti di programmazione (Visual Basic)](../../../api/index.md)
- [Programma con assembly](../../standard/assembly/program.md)
