---
title: Assembly con nomi sicuri
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7cbef005c913d818dba23d85404fe0382fe79f4a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="strong-named-assemblies"></a>Assembly con nomi sicuri
L'assegnazione di un nome sicuro a un assembly permette di creare un'identità univoca e prevenire gli eventuali conflitti con altri assembly.  
  
## <a name="what-makes-a-strong-named-assembly"></a>Come si genera un assembly con nome sicuro?  
 Per generare un assembly con nome sicuro usare la chiave privata corrispondente alla chiave pubblica distribuita con l'assembly, oltre all'assembly stesso. L'assembly include il relativo manifesto, che a sua volta contiene i nomi e gli hash di tutti i file che costituiscono l'assembly. Gli assembly che hanno lo stesso nome sicuro devono essere uguali.  
  
 È possibile assegnare nomi sicuri agli assembly usando Visual Studio o uno strumento da riga di comando. Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) o [Sn.exe (Strong Name Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) (Strumento Nome sicuro (Sn.exe)).  
  
 Nel creare un assembly con nome sicuro è necessario includere il nome in formato testo semplice dell'assembly, il numero di versione, le informazioni facoltative relative alle impostazioni cultura, una firma digitale e la chiave pubblica corrispondente alla chiave privata usata per apporre la firma.  
  
> [!WARNING]
>  Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.  
  
## <a name="why-strong-name-your-assemblies"></a>Perché assegnare nomi sicuri agli assembly?  
 Quando si fa riferimento a un assembly con nome sicuro, ci si aspettano determinate garanzie, quali il controllo delle versioni e la protezione dei nomi. Gli assembly con nome sicuro possono essere installati in Global Assembly Cache, richiesto per abilitare alcuni scenari.  
  
 Gli assembly con nome sicuro risultano utili negli scenari seguenti:  
  
-   Per abilitare il riferimento agli assembly da parte degli assembly con nome sicuro o per concedere a un `friend` l'accesso all'assembly da altri assembly con nome sicuro.  
  
-   Un'app deve accedere a versioni diverse dello stesso assembly. Ciò significa che sono necessarie più versioni di un assembly da caricare affiancate nello stesso dominio di app senza conflitti. Ad esempio , se negli assembly esistono estensioni differenti di una API con lo stesso nome semplice, l'assegnazione di un nome sicuro consente di fornire un'identità univoca a ciascuna versione dell'assembly.  
  
-   Non si vuole influire negativamente sulle prestazioni delle app usando il proprio assembly, quindi si usa un assembly indipendente dal dominio. Questo richiede l'uso di nomi sicuri perché gli assembly indipendenti dal dominio devono essere installati in Global Assembly Cache.  
  
-   Per centralizzare i servizi dell'app applicando i criteri dell'editore che prevedono l'installazione dell'assembly in Global Assembly Cache.  
  
 Gli sviluppatori open source che vogliono ottenere i vantaggi relativi all'identità di un assembly con nome sicuro possono archiviare la chiave privata associata a un assembly nel sistema di controllo del codice sorgente.  
  
## <a name="see-also"></a>Vedere anche  
 [Global Assembly Cache](../../../docs/framework/app-domains/gac.md)  
 [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Sn.exe (strumento Nome sicuro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 [Creazione e utilizzo degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
