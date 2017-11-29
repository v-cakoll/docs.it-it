---
title: Raccolte di schemi OLE DB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9b88308c5dad69ed1ba6f48f525931e94f13ef1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="9d7b6-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="9d7b6-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="9d7b6-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="9d7b6-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d7b6-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="9d7b6-105">Il Driver OLE DB Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="9d7b6-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d7b6-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-106">Tables</span></span>  
  
-   <span data-ttu-id="9d7b6-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7b6-107">Columns</span></span>  
  
-   <span data-ttu-id="9d7b6-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7b6-108">Procedures</span></span>  
  
-   <span data-ttu-id="9d7b6-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7b6-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d7b6-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="9d7b6-110">Catalog</span></span>  
  
-   <span data-ttu-id="9d7b6-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7b6-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9d7b6-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-112">Tables</span></span>  
  
|<span data-ttu-id="9d7b6-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-113">ColumnName</span></span>|<span data-ttu-id="9d7b6-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-115">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-116">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-116">String</span></span>|  
|<span data-ttu-id="9d7b6-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-118">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-118">String</span></span>|  
|<span data-ttu-id="9d7b6-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-119">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-120">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-120">String</span></span>|  
|<span data-ttu-id="9d7b6-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-121">TABLE_TYPE</span></span>|<span data-ttu-id="9d7b6-122">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-122">String</span></span>|  
|<span data-ttu-id="9d7b6-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-123">TABLE_GUID</span></span>|<span data-ttu-id="9d7b6-124">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-124">Guid</span></span>|  
|<span data-ttu-id="9d7b6-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-125">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-126">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-126">String</span></span>|  
|<span data-ttu-id="9d7b6-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-127">TABLE_PROPID</span></span>|<span data-ttu-id="9d7b6-128">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-128">Int64</span></span>|  
|<span data-ttu-id="9d7b6-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-129">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-130">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-131">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d7b6-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7b6-133">Columns</span></span>  
  
|<span data-ttu-id="9d7b6-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-134">ColumnName</span></span>|<span data-ttu-id="9d7b6-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-136">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-137">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-137">String</span></span>|  
|<span data-ttu-id="9d7b6-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-139">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-139">String</span></span>|  
|<span data-ttu-id="9d7b6-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-140">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-141">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-141">String</span></span>|  
|<span data-ttu-id="9d7b6-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-142">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-143">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-143">String</span></span>|  
|<span data-ttu-id="9d7b6-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-144">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-145">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-145">Guid</span></span>|  
|<span data-ttu-id="9d7b6-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-146">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-147">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-147">Int64</span></span>|  
|<span data-ttu-id="9d7b6-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-149">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-149">Int64</span></span>|  
|<span data-ttu-id="9d7b6-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9d7b6-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-151">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9d7b6-153">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-153">String</span></span>|  
|<span data-ttu-id="9d7b6-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="9d7b6-155">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-155">Int64</span></span>|  
|<span data-ttu-id="9d7b6-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-156">IS_NULLABLE</span></span>|<span data-ttu-id="9d7b6-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-157">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-158">DATA_TYPE</span></span>|<span data-ttu-id="9d7b6-159">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-159">Int32</span></span>|  
|<span data-ttu-id="9d7b6-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-160">TYPE_GUID</span></span>|<span data-ttu-id="9d7b6-161">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-161">Guid</span></span>|  
|<span data-ttu-id="9d7b6-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d7b6-163">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-163">Int64</span></span>|  
|<span data-ttu-id="9d7b6-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7b6-165">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-165">Int64</span></span>|  
|<span data-ttu-id="9d7b6-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d7b6-167">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-167">Int32</span></span>|  
|<span data-ttu-id="9d7b6-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d7b6-169">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-169">Int16</span></span>|  
|<span data-ttu-id="9d7b6-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="9d7b6-171">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-171">Int64</span></span>|  
|<span data-ttu-id="9d7b6-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9d7b6-173">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-173">String</span></span>|  
|<span data-ttu-id="9d7b6-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9d7b6-175">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-175">String</span></span>|  
|<span data-ttu-id="9d7b6-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9d7b6-177">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-177">String</span></span>|  
|<span data-ttu-id="9d7b6-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="9d7b6-179">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-179">String</span></span>|  
|<span data-ttu-id="9d7b6-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9d7b6-181">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-181">String</span></span>|  
|<span data-ttu-id="9d7b6-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-182">COLLATION_NAME</span></span>|<span data-ttu-id="9d7b6-183">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-183">String</span></span>|  
|<span data-ttu-id="9d7b6-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9d7b6-185">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-185">String</span></span>|  
|<span data-ttu-id="9d7b6-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9d7b6-187">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-187">String</span></span>|  
|<span data-ttu-id="9d7b6-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-188">DOMAIN_NAME</span></span>|<span data-ttu-id="9d7b6-189">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-189">String</span></span>|  
|<span data-ttu-id="9d7b6-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-190">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-191">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-191">String</span></span>|  
|<span data-ttu-id="9d7b6-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-192">COLUMN_LCID</span></span>|<span data-ttu-id="9d7b6-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-193">Int32</span></span>|  
|<span data-ttu-id="9d7b6-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="9d7b6-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-195">Int32</span></span>|  
|<span data-ttu-id="9d7b6-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-196">COLUMN_SORTID</span></span>|<span data-ttu-id="9d7b6-197">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-197">Int32</span></span>|  
|<span data-ttu-id="9d7b6-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="9d7b6-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="9d7b6-199">Byte[]</span></span>|  
|<span data-ttu-id="9d7b6-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-200">IS_COMPUTED</span></span>|<span data-ttu-id="9d7b6-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d7b6-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7b6-202">Procedures</span></span>  
  
|<span data-ttu-id="9d7b6-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-203">ColumnName</span></span>|<span data-ttu-id="9d7b6-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d7b6-206">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-206">String</span></span>|  
|<span data-ttu-id="9d7b6-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-208">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-208">String</span></span>|  
|<span data-ttu-id="9d7b6-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7b6-210">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-210">String</span></span>|  
|<span data-ttu-id="9d7b6-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d7b6-212">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-212">Int16</span></span>|  
|<span data-ttu-id="9d7b6-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9d7b6-214">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-214">String</span></span>|  
|<span data-ttu-id="9d7b6-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-215">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-216">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-216">String</span></span>|  
|<span data-ttu-id="9d7b6-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-217">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-218">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-219">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9d7b6-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7b6-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9d7b6-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-222">ColumnName</span></span>|<span data-ttu-id="9d7b6-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d7b6-225">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-225">String</span></span>|  
|<span data-ttu-id="9d7b6-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-227">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-227">String</span></span>|  
|<span data-ttu-id="9d7b6-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7b6-229">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-229">String</span></span>|  
|<span data-ttu-id="9d7b6-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-230">PARAMETER_NAME</span></span>|<span data-ttu-id="9d7b6-231">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-231">String</span></span>|  
|<span data-ttu-id="9d7b6-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-233">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-233">Int32</span></span>|  
|<span data-ttu-id="9d7b6-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="9d7b6-235">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-235">Int32</span></span>|  
|<span data-ttu-id="9d7b6-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="9d7b6-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-237">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="9d7b6-239">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-239">String</span></span>|  
|<span data-ttu-id="9d7b6-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-240">IS_NULLABLE</span></span>|<span data-ttu-id="9d7b6-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-241">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-242">DATA_TYPE</span></span>|<span data-ttu-id="9d7b6-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-243">Int32</span></span>|  
|<span data-ttu-id="9d7b6-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d7b6-245">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-245">Int64</span></span>|  
|<span data-ttu-id="9d7b6-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7b6-247">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-247">Int64</span></span>|  
|<span data-ttu-id="9d7b6-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d7b6-249">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-249">Int32</span></span>|  
|<span data-ttu-id="9d7b6-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d7b6-251">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-251">Int16</span></span>|  
|<span data-ttu-id="9d7b6-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-252">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-253">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-253">String</span></span>|  
|<span data-ttu-id="9d7b6-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-254">TYPE_NAME</span></span>|<span data-ttu-id="9d7b6-255">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-255">String</span></span>|  
|<span data-ttu-id="9d7b6-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="9d7b6-257">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="9d7b6-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="9d7b6-258">Catalog</span></span>  
  
|<span data-ttu-id="9d7b6-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-259">ColumnName</span></span>|<span data-ttu-id="9d7b6-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-261">CATALOG_NAME</span></span>|<span data-ttu-id="9d7b6-262">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-262">String</span></span>|  
|<span data-ttu-id="9d7b6-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-263">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-264">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d7b6-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7b6-265">Indexes</span></span>  
  
|<span data-ttu-id="9d7b6-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-266">ColumnName</span></span>|<span data-ttu-id="9d7b6-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-268">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-269">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-269">String</span></span>|  
|<span data-ttu-id="9d7b6-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-271">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-271">String</span></span>|  
|<span data-ttu-id="9d7b6-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-272">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-273">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-273">String</span></span>|  
|<span data-ttu-id="9d7b6-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-274">INDEX_CATALOG</span></span>|<span data-ttu-id="9d7b6-275">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-275">String</span></span>|  
|<span data-ttu-id="9d7b6-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="9d7b6-277">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-277">String</span></span>|  
|<span data-ttu-id="9d7b6-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-278">INDEX_NAME</span></span>|<span data-ttu-id="9d7b6-279">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-279">String</span></span>|  
|<span data-ttu-id="9d7b6-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9d7b6-280">PRIMARY_KEY</span></span>|<span data-ttu-id="9d7b6-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-281">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-282">UNIQUE</span></span>|<span data-ttu-id="9d7b6-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-283">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-284">CLUSTERED</span></span>|<span data-ttu-id="9d7b6-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-285">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-286">TYPE</span></span>|<span data-ttu-id="9d7b6-287">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-287">Int32</span></span>|  
|<span data-ttu-id="9d7b6-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9d7b6-288">FILL_FACTOR</span></span>|<span data-ttu-id="9d7b6-289">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-289">Int32</span></span>|  
|<span data-ttu-id="9d7b6-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-290">INITIAL_SIZE</span></span>|<span data-ttu-id="9d7b6-291">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-291">Int32</span></span>|  
|<span data-ttu-id="9d7b6-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-292">NULLS</span></span>|<span data-ttu-id="9d7b6-293">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-293">Int32</span></span>|  
|<span data-ttu-id="9d7b6-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9d7b6-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-295">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-296">AUTO_UPDATE</span></span>|<span data-ttu-id="9d7b6-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-297">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-298">NULL_COLLATION</span></span>|<span data-ttu-id="9d7b6-299">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-299">Int32</span></span>|  
|<span data-ttu-id="9d7b6-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-301">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-301">Int64</span></span>|  
|<span data-ttu-id="9d7b6-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-302">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-303">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-303">String</span></span>|  
|<span data-ttu-id="9d7b6-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-304">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-305">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-305">Guid</span></span>|  
|<span data-ttu-id="9d7b6-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-306">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-307">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-307">Int64</span></span>|  
|<span data-ttu-id="9d7b6-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-308">COLLATION</span></span>|<span data-ttu-id="9d7b6-309">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-309">Int16</span></span>|  
|<span data-ttu-id="9d7b6-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9d7b6-310">CARDINALITY</span></span>|<span data-ttu-id="9d7b6-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="9d7b6-311">Decimal</span></span>|  
|<span data-ttu-id="9d7b6-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d7b6-312">PAGES</span></span>|<span data-ttu-id="9d7b6-313">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-313">Int32</span></span>|  
|<span data-ttu-id="9d7b6-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-314">FILTER_CONDITION</span></span>|<span data-ttu-id="9d7b6-315">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-315">String</span></span>|  
|<span data-ttu-id="9d7b6-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-316">INTEGRATED</span></span>|<span data-ttu-id="9d7b6-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="9d7b6-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="9d7b6-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="9d7b6-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d7b6-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-320">Tables</span></span>  
  
-   <span data-ttu-id="9d7b6-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7b6-321">Columns</span></span>  
  
-   <span data-ttu-id="9d7b6-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7b6-322">Procedures</span></span>  
  
-   <span data-ttu-id="9d7b6-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7b6-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9d7b6-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7b6-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d7b6-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7b6-325">Views</span></span>  
  
-   <span data-ttu-id="9d7b6-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7b6-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9d7b6-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-327">Tables</span></span>  
  
|<span data-ttu-id="9d7b6-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-328">ColumnName</span></span>|<span data-ttu-id="9d7b6-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-330">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-331">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-331">String</span></span>|  
|<span data-ttu-id="9d7b6-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-333">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-333">String</span></span>|  
|<span data-ttu-id="9d7b6-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-334">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-335">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-335">String</span></span>|  
|<span data-ttu-id="9d7b6-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-336">TABLE_TYPE</span></span>|<span data-ttu-id="9d7b6-337">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-337">String</span></span>|  
|<span data-ttu-id="9d7b6-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-338">TABLE_GUID</span></span>|<span data-ttu-id="9d7b6-339">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-339">Guid</span></span>|  
|<span data-ttu-id="9d7b6-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-340">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-341">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-341">String</span></span>|  
|<span data-ttu-id="9d7b6-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-342">TABLE_PROPID</span></span>|<span data-ttu-id="9d7b6-343">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-343">Int64</span></span>|  
|<span data-ttu-id="9d7b6-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-344">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-345">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-346">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d7b6-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7b6-348">Columns</span></span>  
  
|<span data-ttu-id="9d7b6-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-349">ColumnName</span></span>|<span data-ttu-id="9d7b6-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-351">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-352">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-352">String</span></span>|  
|<span data-ttu-id="9d7b6-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-354">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-354">String</span></span>|  
|<span data-ttu-id="9d7b6-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-355">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-356">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-356">String</span></span>|  
|<span data-ttu-id="9d7b6-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-357">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-358">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-358">String</span></span>|  
|<span data-ttu-id="9d7b6-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-359">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-360">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-360">Guid</span></span>|  
|<span data-ttu-id="9d7b6-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-361">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-362">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-362">Int64</span></span>|  
|<span data-ttu-id="9d7b6-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-364">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-364">Int64</span></span>|  
|<span data-ttu-id="9d7b6-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9d7b6-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-366">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9d7b6-368">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-368">String</span></span>|  
|<span data-ttu-id="9d7b6-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="9d7b6-370">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-370">Int64</span></span>|  
|<span data-ttu-id="9d7b6-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-371">IS_NULLABLE</span></span>|<span data-ttu-id="9d7b6-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-372">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-373">DATA_TYPE</span></span>|<span data-ttu-id="9d7b6-374">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-374">Int32</span></span>|  
|<span data-ttu-id="9d7b6-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-375">TYPE_GUID</span></span>|<span data-ttu-id="9d7b6-376">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-376">Guid</span></span>|  
|<span data-ttu-id="9d7b6-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d7b6-378">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-378">Int64</span></span>|  
|<span data-ttu-id="9d7b6-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7b6-380">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-380">Int64</span></span>|  
|<span data-ttu-id="9d7b6-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d7b6-382">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-382">Int32</span></span>|  
|<span data-ttu-id="9d7b6-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d7b6-384">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-384">Int16</span></span>|  
|<span data-ttu-id="9d7b6-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="9d7b6-386">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-386">Int64</span></span>|  
|<span data-ttu-id="9d7b6-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9d7b6-388">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-388">String</span></span>|  
|<span data-ttu-id="9d7b6-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9d7b6-390">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-390">String</span></span>|  
|<span data-ttu-id="9d7b6-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9d7b6-392">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-392">String</span></span>|  
|<span data-ttu-id="9d7b6-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="9d7b6-394">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-394">String</span></span>|  
|<span data-ttu-id="9d7b6-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9d7b6-396">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-396">String</span></span>|  
|<span data-ttu-id="9d7b6-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-397">COLLATION_NAME</span></span>|<span data-ttu-id="9d7b6-398">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-398">String</span></span>|  
|<span data-ttu-id="9d7b6-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9d7b6-400">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-400">String</span></span>|  
|<span data-ttu-id="9d7b6-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9d7b6-402">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-402">String</span></span>|  
|<span data-ttu-id="9d7b6-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-403">DOMAIN_NAME</span></span>|<span data-ttu-id="9d7b6-404">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-404">String</span></span>|  
|<span data-ttu-id="9d7b6-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-405">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-406">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d7b6-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7b6-407">Procedures</span></span>  
  
|<span data-ttu-id="9d7b6-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-408">ColumnName</span></span>|<span data-ttu-id="9d7b6-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d7b6-411">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-411">String</span></span>|  
|<span data-ttu-id="9d7b6-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-413">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-413">String</span></span>|  
|<span data-ttu-id="9d7b6-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7b6-415">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-415">String</span></span>|  
|<span data-ttu-id="9d7b6-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d7b6-417">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-417">Int16</span></span>|  
|<span data-ttu-id="9d7b6-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9d7b6-419">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-419">String</span></span>|  
|<span data-ttu-id="9d7b6-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-420">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-421">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-421">String</span></span>|  
|<span data-ttu-id="9d7b6-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-422">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-423">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-424">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9d7b6-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7b6-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9d7b6-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-427">ColumnName</span></span>|<span data-ttu-id="9d7b6-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d7b6-430">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-430">String</span></span>|  
|<span data-ttu-id="9d7b6-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-432">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-432">String</span></span>|  
|<span data-ttu-id="9d7b6-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7b6-434">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-434">String</span></span>|  
|<span data-ttu-id="9d7b6-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-435">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-436">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-436">String</span></span>|  
|<span data-ttu-id="9d7b6-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-437">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-438">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-438">Guid</span></span>|  
|<span data-ttu-id="9d7b6-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-439">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-440">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-440">Int64</span></span>|  
|<span data-ttu-id="9d7b6-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="9d7b6-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="9d7b6-442">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-442">Int64</span></span>|  
|<span data-ttu-id="9d7b6-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-444">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-444">Int64</span></span>|  
|<span data-ttu-id="9d7b6-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-445">IS_NULLABLE</span></span>|<span data-ttu-id="9d7b6-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-446">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-447">DATA_TYPE</span></span>|<span data-ttu-id="9d7b6-448">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-448">Int32</span></span>|  
|<span data-ttu-id="9d7b6-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-449">TYPE_GUID</span></span>|<span data-ttu-id="9d7b6-450">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-450">Guid</span></span>|  
|<span data-ttu-id="9d7b6-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d7b6-452">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-452">Int64</span></span>|  
|<span data-ttu-id="9d7b6-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7b6-454">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-454">Int64</span></span>|  
|<span data-ttu-id="9d7b6-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d7b6-456">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-456">Int32</span></span>|  
|<span data-ttu-id="9d7b6-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d7b6-458">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-458">Int16</span></span>|  
|<span data-ttu-id="9d7b6-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-459">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-460">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-460">String</span></span>|  
|<span data-ttu-id="9d7b6-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9d7b6-461">OVERLOAD</span></span>|<span data-ttu-id="9d7b6-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9d7b6-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7b6-463">Views</span></span>  
  
|<span data-ttu-id="9d7b6-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-464">ColumnName</span></span>|<span data-ttu-id="9d7b6-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-466">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-467">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-467">String</span></span>|  
|<span data-ttu-id="9d7b6-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-469">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-469">String</span></span>|  
|<span data-ttu-id="9d7b6-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-470">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-471">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-471">String</span></span>|  
|<span data-ttu-id="9d7b6-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="9d7b6-473">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-473">String</span></span>|  
|<span data-ttu-id="9d7b6-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-474">CHECK_OPTION</span></span>|<span data-ttu-id="9d7b6-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-475">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-476">IS_UPDATABLE</span></span>|<span data-ttu-id="9d7b6-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-477">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-478">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-479">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-479">String</span></span>|  
|<span data-ttu-id="9d7b6-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-480">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-481">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-482">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d7b6-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7b6-484">Indexes</span></span>  
  
|<span data-ttu-id="9d7b6-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-485">ColumnName</span></span>|<span data-ttu-id="9d7b6-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-487">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-488">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-488">String</span></span>|  
|<span data-ttu-id="9d7b6-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-490">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-490">String</span></span>|  
|<span data-ttu-id="9d7b6-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-491">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-492">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-492">String</span></span>|  
|<span data-ttu-id="9d7b6-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-493">INDEX_CATALOG</span></span>|<span data-ttu-id="9d7b6-494">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-494">String</span></span>|  
|<span data-ttu-id="9d7b6-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="9d7b6-496">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-496">String</span></span>|  
|<span data-ttu-id="9d7b6-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-497">INDEX_NAME</span></span>|<span data-ttu-id="9d7b6-498">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-498">String</span></span>|  
|<span data-ttu-id="9d7b6-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9d7b6-499">PRIMARY_KEY</span></span>|<span data-ttu-id="9d7b6-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-500">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-501">UNIQUE</span></span>|<span data-ttu-id="9d7b6-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-502">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-503">CLUSTERED</span></span>|<span data-ttu-id="9d7b6-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-504">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-505">TYPE</span></span>|<span data-ttu-id="9d7b6-506">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-506">Int32</span></span>|  
|<span data-ttu-id="9d7b6-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9d7b6-507">FILL_FACTOR</span></span>|<span data-ttu-id="9d7b6-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-508">Int32</span></span>|  
|<span data-ttu-id="9d7b6-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-509">INITIAL_SIZE</span></span>|<span data-ttu-id="9d7b6-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-510">Int32</span></span>|  
|<span data-ttu-id="9d7b6-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-511">NULLS</span></span>|<span data-ttu-id="9d7b6-512">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-512">Int32</span></span>|  
|<span data-ttu-id="9d7b6-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9d7b6-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-514">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-515">AUTO_UPDATE</span></span>|<span data-ttu-id="9d7b6-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-516">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-517">NULL_COLLATION</span></span>|<span data-ttu-id="9d7b6-518">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-518">Int32</span></span>|  
|<span data-ttu-id="9d7b6-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-520">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-520">Int64</span></span>|  
|<span data-ttu-id="9d7b6-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-521">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-522">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-522">String</span></span>|  
|<span data-ttu-id="9d7b6-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-523">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-524">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-524">Guid</span></span>|  
|<span data-ttu-id="9d7b6-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-525">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-526">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-526">Int64</span></span>|  
|<span data-ttu-id="9d7b6-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-527">COLLATION</span></span>|<span data-ttu-id="9d7b6-528">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-528">Int16</span></span>|  
|<span data-ttu-id="9d7b6-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9d7b6-529">CARDINALITY</span></span>|<span data-ttu-id="9d7b6-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="9d7b6-530">Decimal</span></span>|  
|<span data-ttu-id="9d7b6-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d7b6-531">PAGES</span></span>|<span data-ttu-id="9d7b6-532">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-532">Int32</span></span>|  
|<span data-ttu-id="9d7b6-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-533">FILTER_CONDITION</span></span>|<span data-ttu-id="9d7b6-534">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-534">String</span></span>|  
|<span data-ttu-id="9d7b6-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-535">INTEGRATED</span></span>|<span data-ttu-id="9d7b6-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="9d7b6-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="9d7b6-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="9d7b6-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d7b6-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d7b6-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-539">Tables</span></span>  
  
-   <span data-ttu-id="9d7b6-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7b6-540">Columns</span></span>  
  
-   <span data-ttu-id="9d7b6-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7b6-541">Procedures</span></span>  
  
-   <span data-ttu-id="9d7b6-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7b6-542">Views</span></span>  
  
-   <span data-ttu-id="9d7b6-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7b6-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9d7b6-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7b6-544">Tables</span></span>  
  
|<span data-ttu-id="9d7b6-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-545">ColumnName</span></span>|<span data-ttu-id="9d7b6-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-547">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-548">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-548">String</span></span>|  
|<span data-ttu-id="9d7b6-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-550">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-550">String</span></span>|  
|<span data-ttu-id="9d7b6-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-551">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-552">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-552">String</span></span>|  
|<span data-ttu-id="9d7b6-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-553">TABLE_TYPE</span></span>|<span data-ttu-id="9d7b6-554">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-554">String</span></span>|  
|<span data-ttu-id="9d7b6-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-555">TABLE_GUID</span></span>|<span data-ttu-id="9d7b6-556">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-556">Guid</span></span>|  
|<span data-ttu-id="9d7b6-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-557">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-558">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-558">String</span></span>|  
|<span data-ttu-id="9d7b6-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-559">TABLE_PROPID</span></span>|<span data-ttu-id="9d7b6-560">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-560">Int64</span></span>|  
|<span data-ttu-id="9d7b6-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-561">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-562">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-563">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d7b6-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7b6-565">Columns</span></span>  
  
|<span data-ttu-id="9d7b6-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-566">ColumnName</span></span>|<span data-ttu-id="9d7b6-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-568">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-569">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-569">String</span></span>|  
|<span data-ttu-id="9d7b6-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-571">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-571">String</span></span>|  
|<span data-ttu-id="9d7b6-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-572">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-573">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-573">String</span></span>|  
|<span data-ttu-id="9d7b6-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-574">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-575">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-575">String</span></span>|  
|<span data-ttu-id="9d7b6-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-576">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-577">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-577">Guid</span></span>|  
|<span data-ttu-id="9d7b6-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-578">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-579">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-579">Int64</span></span>|  
|<span data-ttu-id="9d7b6-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-581">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-581">Int64</span></span>|  
|<span data-ttu-id="9d7b6-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9d7b6-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-583">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d7b6-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9d7b6-585">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-585">String</span></span>|  
|<span data-ttu-id="9d7b6-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="9d7b6-587">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-587">Int64</span></span>|  
|<span data-ttu-id="9d7b6-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-588">IS_NULLABLE</span></span>|<span data-ttu-id="9d7b6-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-589">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-590">DATA_TYPE</span></span>|<span data-ttu-id="9d7b6-591">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-591">Int32</span></span>|  
|<span data-ttu-id="9d7b6-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-592">TYPE_GUID</span></span>|<span data-ttu-id="9d7b6-593">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-593">Guid</span></span>|  
|<span data-ttu-id="9d7b6-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d7b6-595">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-595">Int64</span></span>|  
|<span data-ttu-id="9d7b6-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7b6-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7b6-597">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-597">Int64</span></span>|  
|<span data-ttu-id="9d7b6-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d7b6-599">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-599">Int32</span></span>|  
|<span data-ttu-id="9d7b6-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d7b6-601">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-601">Int16</span></span>|  
|<span data-ttu-id="9d7b6-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="9d7b6-603">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-603">Int64</span></span>|  
|<span data-ttu-id="9d7b6-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9d7b6-605">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-605">String</span></span>|  
|<span data-ttu-id="9d7b6-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9d7b6-607">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-607">String</span></span>|  
|<span data-ttu-id="9d7b6-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9d7b6-609">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-609">String</span></span>|  
|<span data-ttu-id="9d7b6-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="9d7b6-611">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-611">String</span></span>|  
|<span data-ttu-id="9d7b6-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9d7b6-613">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-613">String</span></span>|  
|<span data-ttu-id="9d7b6-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-614">COLLATION_NAME</span></span>|<span data-ttu-id="9d7b6-615">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-615">String</span></span>|  
|<span data-ttu-id="9d7b6-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9d7b6-617">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-617">String</span></span>|  
|<span data-ttu-id="9d7b6-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9d7b6-619">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-619">String</span></span>|  
|<span data-ttu-id="9d7b6-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-620">DOMAIN_NAME</span></span>|<span data-ttu-id="9d7b6-621">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-621">String</span></span>|  
|<span data-ttu-id="9d7b6-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-622">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-623">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d7b6-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7b6-624">Procedures</span></span>  
  
|<span data-ttu-id="9d7b6-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-625">ColumnName</span></span>|<span data-ttu-id="9d7b6-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d7b6-628">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-628">String</span></span>|  
|<span data-ttu-id="9d7b6-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-630">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-630">String</span></span>|  
|<span data-ttu-id="9d7b6-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7b6-632">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-632">String</span></span>|  
|<span data-ttu-id="9d7b6-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d7b6-634">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-634">Int16</span></span>|  
|<span data-ttu-id="9d7b6-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9d7b6-636">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-636">String</span></span>|  
|<span data-ttu-id="9d7b6-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-637">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-638">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-638">String</span></span>|  
|<span data-ttu-id="9d7b6-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-639">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-640">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-641">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9d7b6-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7b6-643">Views</span></span>  
  
|<span data-ttu-id="9d7b6-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-644">ColumnName</span></span>|<span data-ttu-id="9d7b6-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-646">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-647">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-647">String</span></span>|  
|<span data-ttu-id="9d7b6-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-649">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-649">String</span></span>|  
|<span data-ttu-id="9d7b6-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-650">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-651">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-651">String</span></span>|  
|<span data-ttu-id="9d7b6-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="9d7b6-653">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-653">String</span></span>|  
|<span data-ttu-id="9d7b6-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-654">CHECK_OPTION</span></span>|<span data-ttu-id="9d7b6-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-655">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-656">IS_UPDATABLE</span></span>|<span data-ttu-id="9d7b6-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-657">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-658">DESCRIPTION</span></span>|<span data-ttu-id="9d7b6-659">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-659">String</span></span>|  
|<span data-ttu-id="9d7b6-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-660">DATE_CREATED</span></span>|<span data-ttu-id="9d7b6-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-661">DateTime</span></span>|  
|<span data-ttu-id="9d7b6-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-662">DATE_MODIFIED</span></span>|<span data-ttu-id="9d7b6-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d7b6-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d7b6-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7b6-664">Indexes</span></span>  
  
|<span data-ttu-id="9d7b6-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7b6-665">ColumnName</span></span>|<span data-ttu-id="9d7b6-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7b6-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-667">TABLE_CATALOG</span></span>|<span data-ttu-id="9d7b6-668">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-668">String</span></span>|  
|<span data-ttu-id="9d7b6-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d7b6-670">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-670">String</span></span>|  
|<span data-ttu-id="9d7b6-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-671">TABLE_NAME</span></span>|<span data-ttu-id="9d7b6-672">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-672">String</span></span>|  
|<span data-ttu-id="9d7b6-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7b6-673">INDEX_CATALOG</span></span>|<span data-ttu-id="9d7b6-674">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-674">String</span></span>|  
|<span data-ttu-id="9d7b6-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7b6-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="9d7b6-676">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-676">String</span></span>|  
|<span data-ttu-id="9d7b6-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-677">INDEX_NAME</span></span>|<span data-ttu-id="9d7b6-678">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-678">String</span></span>|  
|<span data-ttu-id="9d7b6-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9d7b6-679">PRIMARY_KEY</span></span>|<span data-ttu-id="9d7b6-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-680">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-681">UNIQUE</span></span>|<span data-ttu-id="9d7b6-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-682">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-683">CLUSTERED</span></span>|<span data-ttu-id="9d7b6-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-684">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-685">TYPE</span></span>|<span data-ttu-id="9d7b6-686">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-686">Int32</span></span>|  
|<span data-ttu-id="9d7b6-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9d7b6-687">FILL_FACTOR</span></span>|<span data-ttu-id="9d7b6-688">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-688">Int32</span></span>|  
|<span data-ttu-id="9d7b6-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-689">INITIAL_SIZE</span></span>|<span data-ttu-id="9d7b6-690">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-690">Int32</span></span>|  
|<span data-ttu-id="9d7b6-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-691">NULLS</span></span>|<span data-ttu-id="9d7b6-692">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-692">Int32</span></span>|  
|<span data-ttu-id="9d7b6-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7b6-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9d7b6-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-694">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d7b6-695">AUTO_UPDATE</span></span>|<span data-ttu-id="9d7b6-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d7b6-696">Boolean</span></span>|  
|<span data-ttu-id="9d7b6-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-697">NULL_COLLATION</span></span>|<span data-ttu-id="9d7b6-698">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-698">Int32</span></span>|  
|<span data-ttu-id="9d7b6-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7b6-700">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-700">Int64</span></span>|  
|<span data-ttu-id="9d7b6-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7b6-701">COLUMN_NAME</span></span>|<span data-ttu-id="9d7b6-702">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-702">String</span></span>|  
|<span data-ttu-id="9d7b6-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-703">COLUMN_GUID</span></span>|<span data-ttu-id="9d7b6-704">Guid</span><span class="sxs-lookup"><span data-stu-id="9d7b6-704">Guid</span></span>|  
|<span data-ttu-id="9d7b6-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d7b6-705">COLUMN_PROPID</span></span>|<span data-ttu-id="9d7b6-706">Int64</span><span class="sxs-lookup"><span data-stu-id="9d7b6-706">Int64</span></span>|  
|<span data-ttu-id="9d7b6-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-707">COLLATION</span></span>|<span data-ttu-id="9d7b6-708">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7b6-708">Int16</span></span>|  
|<span data-ttu-id="9d7b6-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9d7b6-709">CARDINALITY</span></span>|<span data-ttu-id="9d7b6-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="9d7b6-710">Decimal</span></span>|  
|<span data-ttu-id="9d7b6-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d7b6-711">PAGES</span></span>|<span data-ttu-id="9d7b6-712">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7b6-712">Int32</span></span>|  
|<span data-ttu-id="9d7b6-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d7b6-713">FILTER_CONDITION</span></span>|<span data-ttu-id="9d7b6-714">String</span><span class="sxs-lookup"><span data-stu-id="9d7b6-714">String</span></span>|  
|<span data-ttu-id="9d7b6-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9d7b6-715">INTEGRATED</span></span>|<span data-ttu-id="9d7b6-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="9d7b6-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d7b6-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d7b6-717">See Also</span></span>  
 [<span data-ttu-id="9d7b6-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9d7b6-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
