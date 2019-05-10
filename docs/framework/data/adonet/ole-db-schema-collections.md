---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645902"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="31bfa-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="31bfa-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="31bfa-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="31bfa-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="31bfa-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="31bfa-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="31bfa-105">Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="31bfa-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="31bfa-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="31bfa-106">Tables</span></span>  
  
- <span data-ttu-id="31bfa-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="31bfa-107">Columns</span></span>  
  
- <span data-ttu-id="31bfa-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="31bfa-108">Procedures</span></span>  
  
- <span data-ttu-id="31bfa-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="31bfa-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="31bfa-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="31bfa-110">Catalog</span></span>  
  
- <span data-ttu-id="31bfa-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="31bfa-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="31bfa-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="31bfa-112">Tables</span></span>  
  
|<span data-ttu-id="31bfa-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-113">ColumnName</span></span>|<span data-ttu-id="31bfa-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-115">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-116">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-116">String</span></span>|  
|<span data-ttu-id="31bfa-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-118">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-118">String</span></span>|  
|<span data-ttu-id="31bfa-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-119">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-120">String</span></span>|  
|<span data-ttu-id="31bfa-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-121">TABLE_TYPE</span></span>|<span data-ttu-id="31bfa-122">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-122">String</span></span>|  
|<span data-ttu-id="31bfa-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-123">TABLE_GUID</span></span>|<span data-ttu-id="31bfa-124">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-124">Guid</span></span>|  
|<span data-ttu-id="31bfa-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-125">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-126">String</span></span>|  
|<span data-ttu-id="31bfa-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-127">TABLE_PROPID</span></span>|<span data-ttu-id="31bfa-128">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-128">Int64</span></span>|  
|<span data-ttu-id="31bfa-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-129">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-130">DateTime</span></span>|  
|<span data-ttu-id="31bfa-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-131">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="31bfa-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="31bfa-133">Columns</span></span>  
  
|<span data-ttu-id="31bfa-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-134">ColumnName</span></span>|<span data-ttu-id="31bfa-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-136">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-137">String</span></span>|  
|<span data-ttu-id="31bfa-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-139">String</span></span>|  
|<span data-ttu-id="31bfa-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-140">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-141">String</span></span>|  
|<span data-ttu-id="31bfa-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-142">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-143">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-143">String</span></span>|  
|<span data-ttu-id="31bfa-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-144">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-145">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-145">Guid</span></span>|  
|<span data-ttu-id="31bfa-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-146">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-147">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-147">Int64</span></span>|  
|<span data-ttu-id="31bfa-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-149">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-149">Int64</span></span>|  
|<span data-ttu-id="31bfa-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="31bfa-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-151">Boolean</span></span>|  
|<span data-ttu-id="31bfa-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="31bfa-153">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-153">String</span></span>|  
|<span data-ttu-id="31bfa-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="31bfa-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="31bfa-155">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-155">Int64</span></span>|  
|<span data-ttu-id="31bfa-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-156">IS_NULLABLE</span></span>|<span data-ttu-id="31bfa-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-157">Boolean</span></span>|  
|<span data-ttu-id="31bfa-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-158">DATA_TYPE</span></span>|<span data-ttu-id="31bfa-159">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-159">Int32</span></span>|  
|<span data-ttu-id="31bfa-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-160">TYPE_GUID</span></span>|<span data-ttu-id="31bfa-161">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-161">Guid</span></span>|  
|<span data-ttu-id="31bfa-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="31bfa-163">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-163">Int64</span></span>|  
|<span data-ttu-id="31bfa-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="31bfa-165">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-165">Int64</span></span>|  
|<span data-ttu-id="31bfa-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="31bfa-167">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-167">Int32</span></span>|  
|<span data-ttu-id="31bfa-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="31bfa-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="31bfa-169">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-169">Int16</span></span>|  
|<span data-ttu-id="31bfa-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="31bfa-171">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-171">Int64</span></span>|  
|<span data-ttu-id="31bfa-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="31bfa-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-173">String</span></span>|  
|<span data-ttu-id="31bfa-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="31bfa-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-175">String</span></span>|  
|<span data-ttu-id="31bfa-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="31bfa-177">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-177">String</span></span>|  
|<span data-ttu-id="31bfa-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="31bfa-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-179">String</span></span>|  
|<span data-ttu-id="31bfa-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="31bfa-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-181">String</span></span>|  
|<span data-ttu-id="31bfa-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-182">COLLATION_NAME</span></span>|<span data-ttu-id="31bfa-183">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-183">String</span></span>|  
|<span data-ttu-id="31bfa-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="31bfa-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-185">String</span></span>|  
|<span data-ttu-id="31bfa-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="31bfa-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-187">String</span></span>|  
|<span data-ttu-id="31bfa-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-188">DOMAIN_NAME</span></span>|<span data-ttu-id="31bfa-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-189">String</span></span>|  
|<span data-ttu-id="31bfa-190">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-190">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-191">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-191">String</span></span>|  
|<span data-ttu-id="31bfa-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="31bfa-192">COLUMN_LCID</span></span>|<span data-ttu-id="31bfa-193">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-193">Int32</span></span>|  
|<span data-ttu-id="31bfa-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="31bfa-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="31bfa-195">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-195">Int32</span></span>|  
|<span data-ttu-id="31bfa-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="31bfa-196">COLUMN_SORTID</span></span>|<span data-ttu-id="31bfa-197">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-197">Int32</span></span>|  
|<span data-ttu-id="31bfa-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="31bfa-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="31bfa-199">Byte[]</span></span>|  
|<span data-ttu-id="31bfa-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="31bfa-200">IS_COMPUTED</span></span>|<span data-ttu-id="31bfa-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="31bfa-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="31bfa-202">Procedures</span></span>  
  
|<span data-ttu-id="31bfa-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-203">ColumnName</span></span>|<span data-ttu-id="31bfa-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="31bfa-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-206">String</span></span>|  
|<span data-ttu-id="31bfa-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="31bfa-208">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-208">String</span></span>|  
|<span data-ttu-id="31bfa-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="31bfa-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-210">String</span></span>|  
|<span data-ttu-id="31bfa-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="31bfa-212">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-212">Int16</span></span>|  
|<span data-ttu-id="31bfa-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="31bfa-214">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-214">String</span></span>|  
|<span data-ttu-id="31bfa-215">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-215">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-216">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-216">String</span></span>|  
|<span data-ttu-id="31bfa-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-217">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-218">DateTime</span></span>|  
|<span data-ttu-id="31bfa-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-219">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="31bfa-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="31bfa-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="31bfa-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-222">ColumnName</span></span>|<span data-ttu-id="31bfa-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="31bfa-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-225">String</span></span>|  
|<span data-ttu-id="31bfa-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="31bfa-227">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-227">String</span></span>|  
|<span data-ttu-id="31bfa-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="31bfa-229">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-229">String</span></span>|  
|<span data-ttu-id="31bfa-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-230">PARAMETER_NAME</span></span>|<span data-ttu-id="31bfa-231">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-231">String</span></span>|  
|<span data-ttu-id="31bfa-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-233">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-233">Int32</span></span>|  
|<span data-ttu-id="31bfa-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="31bfa-235">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-235">Int32</span></span>|  
|<span data-ttu-id="31bfa-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="31bfa-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-237">Boolean</span></span>|  
|<span data-ttu-id="31bfa-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="31bfa-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-239">String</span></span>|  
|<span data-ttu-id="31bfa-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-240">IS_NULLABLE</span></span>|<span data-ttu-id="31bfa-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-241">Boolean</span></span>|  
|<span data-ttu-id="31bfa-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-242">DATA_TYPE</span></span>|<span data-ttu-id="31bfa-243">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-243">Int32</span></span>|  
|<span data-ttu-id="31bfa-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="31bfa-245">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-245">Int64</span></span>|  
|<span data-ttu-id="31bfa-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="31bfa-247">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-247">Int64</span></span>|  
|<span data-ttu-id="31bfa-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="31bfa-249">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-249">Int32</span></span>|  
|<span data-ttu-id="31bfa-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="31bfa-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="31bfa-251">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-251">Int16</span></span>|  
|<span data-ttu-id="31bfa-252">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-252">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-253">String</span></span>|  
|<span data-ttu-id="31bfa-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-254">TYPE_NAME</span></span>|<span data-ttu-id="31bfa-255">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-255">String</span></span>|  
|<span data-ttu-id="31bfa-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="31bfa-257">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="31bfa-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="31bfa-258">Catalog</span></span>  
  
|<span data-ttu-id="31bfa-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-259">ColumnName</span></span>|<span data-ttu-id="31bfa-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-261">CATALOG_NAME</span></span>|<span data-ttu-id="31bfa-262">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-262">String</span></span>|  
|<span data-ttu-id="31bfa-263">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-263">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-264">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="31bfa-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="31bfa-265">Indexes</span></span>  
  
|<span data-ttu-id="31bfa-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-266">ColumnName</span></span>|<span data-ttu-id="31bfa-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-268">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-269">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-269">String</span></span>|  
|<span data-ttu-id="31bfa-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-271">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-271">String</span></span>|  
|<span data-ttu-id="31bfa-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-272">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-273">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-273">String</span></span>|  
|<span data-ttu-id="31bfa-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-274">INDEX_CATALOG</span></span>|<span data-ttu-id="31bfa-275">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-275">String</span></span>|  
|<span data-ttu-id="31bfa-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="31bfa-277">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-277">String</span></span>|  
|<span data-ttu-id="31bfa-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-278">INDEX_NAME</span></span>|<span data-ttu-id="31bfa-279">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-279">String</span></span>|  
|<span data-ttu-id="31bfa-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="31bfa-280">PRIMARY_KEY</span></span>|<span data-ttu-id="31bfa-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-281">Boolean</span></span>|  
|<span data-ttu-id="31bfa-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="31bfa-282">UNIQUE</span></span>|<span data-ttu-id="31bfa-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-283">Boolean</span></span>|  
|<span data-ttu-id="31bfa-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="31bfa-284">CLUSTERED</span></span>|<span data-ttu-id="31bfa-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-285">Boolean</span></span>|  
|<span data-ttu-id="31bfa-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-286">TYPE</span></span>|<span data-ttu-id="31bfa-287">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-287">Int32</span></span>|  
|<span data-ttu-id="31bfa-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="31bfa-288">FILL_FACTOR</span></span>|<span data-ttu-id="31bfa-289">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-289">Int32</span></span>|  
|<span data-ttu-id="31bfa-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="31bfa-290">INITIAL_SIZE</span></span>|<span data-ttu-id="31bfa-291">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-291">Int32</span></span>|  
|<span data-ttu-id="31bfa-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="31bfa-292">NULLS</span></span>|<span data-ttu-id="31bfa-293">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-293">Int32</span></span>|  
|<span data-ttu-id="31bfa-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="31bfa-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="31bfa-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-295">Boolean</span></span>|  
|<span data-ttu-id="31bfa-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="31bfa-296">AUTO_UPDATE</span></span>|<span data-ttu-id="31bfa-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-297">Boolean</span></span>|  
|<span data-ttu-id="31bfa-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-298">NULL_COLLATION</span></span>|<span data-ttu-id="31bfa-299">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-299">Int32</span></span>|  
|<span data-ttu-id="31bfa-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-301">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-301">Int64</span></span>|  
|<span data-ttu-id="31bfa-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-302">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-303">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-303">String</span></span>|  
|<span data-ttu-id="31bfa-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-304">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-305">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-305">Guid</span></span>|  
|<span data-ttu-id="31bfa-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-306">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-307">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-307">Int64</span></span>|  
|<span data-ttu-id="31bfa-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-308">COLLATION</span></span>|<span data-ttu-id="31bfa-309">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-309">Int16</span></span>|  
|<span data-ttu-id="31bfa-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="31bfa-310">CARDINALITY</span></span>|<span data-ttu-id="31bfa-311">Decimale</span><span class="sxs-lookup"><span data-stu-id="31bfa-311">Decimal</span></span>|  
|<span data-ttu-id="31bfa-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="31bfa-312">PAGES</span></span>|<span data-ttu-id="31bfa-313">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-313">Int32</span></span>|  
|<span data-ttu-id="31bfa-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-314">FILTER_CONDITION</span></span>|<span data-ttu-id="31bfa-315">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-315">String</span></span>|  
|<span data-ttu-id="31bfa-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-316">INTEGRATED</span></span>|<span data-ttu-id="31bfa-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="31bfa-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="31bfa-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="31bfa-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="31bfa-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="31bfa-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="31bfa-320">Tables</span></span>  
  
- <span data-ttu-id="31bfa-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="31bfa-321">Columns</span></span>  
  
- <span data-ttu-id="31bfa-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="31bfa-322">Procedures</span></span>  
  
- <span data-ttu-id="31bfa-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="31bfa-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="31bfa-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="31bfa-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="31bfa-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="31bfa-325">Views</span></span>  
  
- <span data-ttu-id="31bfa-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="31bfa-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="31bfa-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="31bfa-327">Tables</span></span>  
  
|<span data-ttu-id="31bfa-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-328">ColumnName</span></span>|<span data-ttu-id="31bfa-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-330">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-331">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-331">String</span></span>|  
|<span data-ttu-id="31bfa-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-333">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-333">String</span></span>|  
|<span data-ttu-id="31bfa-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-334">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-335">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-335">String</span></span>|  
|<span data-ttu-id="31bfa-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-336">TABLE_TYPE</span></span>|<span data-ttu-id="31bfa-337">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-337">String</span></span>|  
|<span data-ttu-id="31bfa-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-338">TABLE_GUID</span></span>|<span data-ttu-id="31bfa-339">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-339">Guid</span></span>|  
|<span data-ttu-id="31bfa-340">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-340">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-341">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-341">String</span></span>|  
|<span data-ttu-id="31bfa-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-342">TABLE_PROPID</span></span>|<span data-ttu-id="31bfa-343">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-343">Int64</span></span>|  
|<span data-ttu-id="31bfa-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-344">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-345">DateTime</span></span>|  
|<span data-ttu-id="31bfa-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-346">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="31bfa-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="31bfa-348">Columns</span></span>  
  
|<span data-ttu-id="31bfa-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-349">ColumnName</span></span>|<span data-ttu-id="31bfa-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-351">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-352">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-352">String</span></span>|  
|<span data-ttu-id="31bfa-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-354">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-354">String</span></span>|  
|<span data-ttu-id="31bfa-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-355">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-356">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-356">String</span></span>|  
|<span data-ttu-id="31bfa-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-357">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-358">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-358">String</span></span>|  
|<span data-ttu-id="31bfa-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-359">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-360">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-360">Guid</span></span>|  
|<span data-ttu-id="31bfa-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-361">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-362">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-362">Int64</span></span>|  
|<span data-ttu-id="31bfa-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-364">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-364">Int64</span></span>|  
|<span data-ttu-id="31bfa-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="31bfa-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-366">Boolean</span></span>|  
|<span data-ttu-id="31bfa-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="31bfa-368">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-368">String</span></span>|  
|<span data-ttu-id="31bfa-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="31bfa-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="31bfa-370">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-370">Int64</span></span>|  
|<span data-ttu-id="31bfa-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-371">IS_NULLABLE</span></span>|<span data-ttu-id="31bfa-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-372">Boolean</span></span>|  
|<span data-ttu-id="31bfa-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-373">DATA_TYPE</span></span>|<span data-ttu-id="31bfa-374">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-374">Int32</span></span>|  
|<span data-ttu-id="31bfa-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-375">TYPE_GUID</span></span>|<span data-ttu-id="31bfa-376">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-376">Guid</span></span>|  
|<span data-ttu-id="31bfa-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="31bfa-378">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-378">Int64</span></span>|  
|<span data-ttu-id="31bfa-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="31bfa-380">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-380">Int64</span></span>|  
|<span data-ttu-id="31bfa-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="31bfa-382">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-382">Int32</span></span>|  
|<span data-ttu-id="31bfa-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="31bfa-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="31bfa-384">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-384">Int16</span></span>|  
|<span data-ttu-id="31bfa-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="31bfa-386">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-386">Int64</span></span>|  
|<span data-ttu-id="31bfa-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="31bfa-388">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-388">String</span></span>|  
|<span data-ttu-id="31bfa-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="31bfa-390">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-390">String</span></span>|  
|<span data-ttu-id="31bfa-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="31bfa-392">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-392">String</span></span>|  
|<span data-ttu-id="31bfa-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="31bfa-394">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-394">String</span></span>|  
|<span data-ttu-id="31bfa-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="31bfa-396">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-396">String</span></span>|  
|<span data-ttu-id="31bfa-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-397">COLLATION_NAME</span></span>|<span data-ttu-id="31bfa-398">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-398">String</span></span>|  
|<span data-ttu-id="31bfa-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="31bfa-400">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-400">String</span></span>|  
|<span data-ttu-id="31bfa-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="31bfa-402">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-402">String</span></span>|  
|<span data-ttu-id="31bfa-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-403">DOMAIN_NAME</span></span>|<span data-ttu-id="31bfa-404">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-404">String</span></span>|  
|<span data-ttu-id="31bfa-405">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-405">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-406">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="31bfa-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="31bfa-407">Procedures</span></span>  
  
|<span data-ttu-id="31bfa-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-408">ColumnName</span></span>|<span data-ttu-id="31bfa-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="31bfa-411">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-411">String</span></span>|  
|<span data-ttu-id="31bfa-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="31bfa-413">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-413">String</span></span>|  
|<span data-ttu-id="31bfa-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="31bfa-415">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-415">String</span></span>|  
|<span data-ttu-id="31bfa-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="31bfa-417">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-417">Int16</span></span>|  
|<span data-ttu-id="31bfa-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="31bfa-419">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-419">String</span></span>|  
|<span data-ttu-id="31bfa-420">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-420">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-421">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-421">String</span></span>|  
|<span data-ttu-id="31bfa-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-422">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-423">DateTime</span></span>|  
|<span data-ttu-id="31bfa-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-424">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="31bfa-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="31bfa-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="31bfa-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-427">ColumnName</span></span>|<span data-ttu-id="31bfa-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="31bfa-430">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-430">String</span></span>|  
|<span data-ttu-id="31bfa-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="31bfa-432">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-432">String</span></span>|  
|<span data-ttu-id="31bfa-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="31bfa-434">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-434">String</span></span>|  
|<span data-ttu-id="31bfa-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-435">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-436">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-436">String</span></span>|  
|<span data-ttu-id="31bfa-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-437">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-438">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-438">Guid</span></span>|  
|<span data-ttu-id="31bfa-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-439">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-440">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-440">Int64</span></span>|  
|<span data-ttu-id="31bfa-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="31bfa-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="31bfa-442">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-442">Int64</span></span>|  
|<span data-ttu-id="31bfa-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-444">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-444">Int64</span></span>|  
|<span data-ttu-id="31bfa-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-445">IS_NULLABLE</span></span>|<span data-ttu-id="31bfa-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-446">Boolean</span></span>|  
|<span data-ttu-id="31bfa-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-447">DATA_TYPE</span></span>|<span data-ttu-id="31bfa-448">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-448">Int32</span></span>|  
|<span data-ttu-id="31bfa-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-449">TYPE_GUID</span></span>|<span data-ttu-id="31bfa-450">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-450">Guid</span></span>|  
|<span data-ttu-id="31bfa-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="31bfa-452">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-452">Int64</span></span>|  
|<span data-ttu-id="31bfa-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="31bfa-454">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-454">Int64</span></span>|  
|<span data-ttu-id="31bfa-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="31bfa-456">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-456">Int32</span></span>|  
|<span data-ttu-id="31bfa-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="31bfa-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="31bfa-458">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-458">Int16</span></span>|  
|<span data-ttu-id="31bfa-459">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-459">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-460">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-460">String</span></span>|  
|<span data-ttu-id="31bfa-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="31bfa-461">OVERLOAD</span></span>|<span data-ttu-id="31bfa-462">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="31bfa-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="31bfa-463">Views</span></span>  
  
|<span data-ttu-id="31bfa-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-464">ColumnName</span></span>|<span data-ttu-id="31bfa-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-466">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-467">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-467">String</span></span>|  
|<span data-ttu-id="31bfa-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-469">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-469">String</span></span>|  
|<span data-ttu-id="31bfa-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-470">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-471">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-471">String</span></span>|  
|<span data-ttu-id="31bfa-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="31bfa-473">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-473">String</span></span>|  
|<span data-ttu-id="31bfa-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="31bfa-474">CHECK_OPTION</span></span>|<span data-ttu-id="31bfa-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-475">Boolean</span></span>|  
|<span data-ttu-id="31bfa-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-476">IS_UPDATABLE</span></span>|<span data-ttu-id="31bfa-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-477">Boolean</span></span>|  
|<span data-ttu-id="31bfa-478">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-478">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-479">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-479">String</span></span>|  
|<span data-ttu-id="31bfa-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-480">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-481">DateTime</span></span>|  
|<span data-ttu-id="31bfa-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-482">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="31bfa-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="31bfa-484">Indexes</span></span>  
  
|<span data-ttu-id="31bfa-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-485">ColumnName</span></span>|<span data-ttu-id="31bfa-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-487">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-488">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-488">String</span></span>|  
|<span data-ttu-id="31bfa-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-490">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-490">String</span></span>|  
|<span data-ttu-id="31bfa-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-491">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-492">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-492">String</span></span>|  
|<span data-ttu-id="31bfa-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-493">INDEX_CATALOG</span></span>|<span data-ttu-id="31bfa-494">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-494">String</span></span>|  
|<span data-ttu-id="31bfa-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="31bfa-496">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-496">String</span></span>|  
|<span data-ttu-id="31bfa-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-497">INDEX_NAME</span></span>|<span data-ttu-id="31bfa-498">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-498">String</span></span>|  
|<span data-ttu-id="31bfa-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="31bfa-499">PRIMARY_KEY</span></span>|<span data-ttu-id="31bfa-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-500">Boolean</span></span>|  
|<span data-ttu-id="31bfa-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="31bfa-501">UNIQUE</span></span>|<span data-ttu-id="31bfa-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-502">Boolean</span></span>|  
|<span data-ttu-id="31bfa-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="31bfa-503">CLUSTERED</span></span>|<span data-ttu-id="31bfa-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-504">Boolean</span></span>|  
|<span data-ttu-id="31bfa-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-505">TYPE</span></span>|<span data-ttu-id="31bfa-506">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-506">Int32</span></span>|  
|<span data-ttu-id="31bfa-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="31bfa-507">FILL_FACTOR</span></span>|<span data-ttu-id="31bfa-508">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-508">Int32</span></span>|  
|<span data-ttu-id="31bfa-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="31bfa-509">INITIAL_SIZE</span></span>|<span data-ttu-id="31bfa-510">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-510">Int32</span></span>|  
|<span data-ttu-id="31bfa-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="31bfa-511">NULLS</span></span>|<span data-ttu-id="31bfa-512">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-512">Int32</span></span>|  
|<span data-ttu-id="31bfa-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="31bfa-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="31bfa-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-514">Boolean</span></span>|  
|<span data-ttu-id="31bfa-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="31bfa-515">AUTO_UPDATE</span></span>|<span data-ttu-id="31bfa-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-516">Boolean</span></span>|  
|<span data-ttu-id="31bfa-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-517">NULL_COLLATION</span></span>|<span data-ttu-id="31bfa-518">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-518">Int32</span></span>|  
|<span data-ttu-id="31bfa-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-520">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-520">Int64</span></span>|  
|<span data-ttu-id="31bfa-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-521">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-522">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-522">String</span></span>|  
|<span data-ttu-id="31bfa-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-523">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-524">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-524">Guid</span></span>|  
|<span data-ttu-id="31bfa-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-525">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-526">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-526">Int64</span></span>|  
|<span data-ttu-id="31bfa-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-527">COLLATION</span></span>|<span data-ttu-id="31bfa-528">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-528">Int16</span></span>|  
|<span data-ttu-id="31bfa-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="31bfa-529">CARDINALITY</span></span>|<span data-ttu-id="31bfa-530">Decimale</span><span class="sxs-lookup"><span data-stu-id="31bfa-530">Decimal</span></span>|  
|<span data-ttu-id="31bfa-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="31bfa-531">PAGES</span></span>|<span data-ttu-id="31bfa-532">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-532">Int32</span></span>|  
|<span data-ttu-id="31bfa-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-533">FILTER_CONDITION</span></span>|<span data-ttu-id="31bfa-534">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-534">String</span></span>|  
|<span data-ttu-id="31bfa-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-535">INTEGRATED</span></span>|<span data-ttu-id="31bfa-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="31bfa-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="31bfa-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="31bfa-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="31bfa-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="31bfa-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="31bfa-539">Tables</span></span>  
  
- <span data-ttu-id="31bfa-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="31bfa-540">Columns</span></span>  
  
- <span data-ttu-id="31bfa-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="31bfa-541">Procedures</span></span>  
  
- <span data-ttu-id="31bfa-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="31bfa-542">Views</span></span>  
  
- <span data-ttu-id="31bfa-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="31bfa-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="31bfa-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="31bfa-544">Tables</span></span>  
  
|<span data-ttu-id="31bfa-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-545">ColumnName</span></span>|<span data-ttu-id="31bfa-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-547">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-548">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-548">String</span></span>|  
|<span data-ttu-id="31bfa-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-550">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-550">String</span></span>|  
|<span data-ttu-id="31bfa-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-551">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-552">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-552">String</span></span>|  
|<span data-ttu-id="31bfa-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-553">TABLE_TYPE</span></span>|<span data-ttu-id="31bfa-554">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-554">String</span></span>|  
|<span data-ttu-id="31bfa-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-555">TABLE_GUID</span></span>|<span data-ttu-id="31bfa-556">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-556">Guid</span></span>|  
|<span data-ttu-id="31bfa-557">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-557">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-558">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-558">String</span></span>|  
|<span data-ttu-id="31bfa-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-559">TABLE_PROPID</span></span>|<span data-ttu-id="31bfa-560">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-560">Int64</span></span>|  
|<span data-ttu-id="31bfa-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-561">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-562">DateTime</span></span>|  
|<span data-ttu-id="31bfa-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-563">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="31bfa-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="31bfa-565">Columns</span></span>  
  
|<span data-ttu-id="31bfa-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-566">ColumnName</span></span>|<span data-ttu-id="31bfa-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-568">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-569">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-569">String</span></span>|  
|<span data-ttu-id="31bfa-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-571">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-571">String</span></span>|  
|<span data-ttu-id="31bfa-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-572">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-573">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-573">String</span></span>|  
|<span data-ttu-id="31bfa-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-574">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-575">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-575">String</span></span>|  
|<span data-ttu-id="31bfa-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-576">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-577">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-577">Guid</span></span>|  
|<span data-ttu-id="31bfa-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-578">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-579">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-579">Int64</span></span>|  
|<span data-ttu-id="31bfa-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-581">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-581">Int64</span></span>|  
|<span data-ttu-id="31bfa-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="31bfa-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-583">Boolean</span></span>|  
|<span data-ttu-id="31bfa-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="31bfa-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="31bfa-585">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-585">String</span></span>|  
|<span data-ttu-id="31bfa-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="31bfa-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="31bfa-587">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-587">Int64</span></span>|  
|<span data-ttu-id="31bfa-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-588">IS_NULLABLE</span></span>|<span data-ttu-id="31bfa-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-589">Boolean</span></span>|  
|<span data-ttu-id="31bfa-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-590">DATA_TYPE</span></span>|<span data-ttu-id="31bfa-591">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-591">Int32</span></span>|  
|<span data-ttu-id="31bfa-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-592">TYPE_GUID</span></span>|<span data-ttu-id="31bfa-593">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-593">Guid</span></span>|  
|<span data-ttu-id="31bfa-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="31bfa-595">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-595">Int64</span></span>|  
|<span data-ttu-id="31bfa-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="31bfa-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="31bfa-597">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-597">Int64</span></span>|  
|<span data-ttu-id="31bfa-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="31bfa-599">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-599">Int32</span></span>|  
|<span data-ttu-id="31bfa-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="31bfa-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="31bfa-601">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-601">Int16</span></span>|  
|<span data-ttu-id="31bfa-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="31bfa-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="31bfa-603">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-603">Int64</span></span>|  
|<span data-ttu-id="31bfa-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="31bfa-605">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-605">String</span></span>|  
|<span data-ttu-id="31bfa-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="31bfa-607">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-607">String</span></span>|  
|<span data-ttu-id="31bfa-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="31bfa-609">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-609">String</span></span>|  
|<span data-ttu-id="31bfa-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="31bfa-611">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-611">String</span></span>|  
|<span data-ttu-id="31bfa-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="31bfa-613">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-613">String</span></span>|  
|<span data-ttu-id="31bfa-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-614">COLLATION_NAME</span></span>|<span data-ttu-id="31bfa-615">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-615">String</span></span>|  
|<span data-ttu-id="31bfa-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="31bfa-617">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-617">String</span></span>|  
|<span data-ttu-id="31bfa-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="31bfa-619">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-619">String</span></span>|  
|<span data-ttu-id="31bfa-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-620">DOMAIN_NAME</span></span>|<span data-ttu-id="31bfa-621">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-621">String</span></span>|  
|<span data-ttu-id="31bfa-622">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-622">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-623">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="31bfa-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="31bfa-624">Procedures</span></span>  
  
|<span data-ttu-id="31bfa-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-625">ColumnName</span></span>|<span data-ttu-id="31bfa-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="31bfa-628">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-628">String</span></span>|  
|<span data-ttu-id="31bfa-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="31bfa-630">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-630">String</span></span>|  
|<span data-ttu-id="31bfa-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="31bfa-632">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-632">String</span></span>|  
|<span data-ttu-id="31bfa-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="31bfa-634">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-634">Int16</span></span>|  
|<span data-ttu-id="31bfa-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="31bfa-636">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-636">String</span></span>|  
|<span data-ttu-id="31bfa-637">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-637">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-638">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-638">String</span></span>|  
|<span data-ttu-id="31bfa-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-639">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-640">DateTime</span></span>|  
|<span data-ttu-id="31bfa-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-641">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="31bfa-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="31bfa-643">Views</span></span>  
  
|<span data-ttu-id="31bfa-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-644">ColumnName</span></span>|<span data-ttu-id="31bfa-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-646">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-647">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-647">String</span></span>|  
|<span data-ttu-id="31bfa-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-649">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-649">String</span></span>|  
|<span data-ttu-id="31bfa-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-650">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-651">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-651">String</span></span>|  
|<span data-ttu-id="31bfa-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="31bfa-653">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-653">String</span></span>|  
|<span data-ttu-id="31bfa-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="31bfa-654">CHECK_OPTION</span></span>|<span data-ttu-id="31bfa-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-655">Boolean</span></span>|  
|<span data-ttu-id="31bfa-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="31bfa-656">IS_UPDATABLE</span></span>|<span data-ttu-id="31bfa-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-657">Boolean</span></span>|  
|<span data-ttu-id="31bfa-658">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31bfa-658">DESCRIPTION</span></span>|<span data-ttu-id="31bfa-659">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-659">String</span></span>|  
|<span data-ttu-id="31bfa-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-660">DATE_CREATED</span></span>|<span data-ttu-id="31bfa-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-661">DateTime</span></span>|  
|<span data-ttu-id="31bfa-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="31bfa-662">DATE_MODIFIED</span></span>|<span data-ttu-id="31bfa-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="31bfa-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="31bfa-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="31bfa-664">Indexes</span></span>  
  
|<span data-ttu-id="31bfa-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="31bfa-665">ColumnName</span></span>|<span data-ttu-id="31bfa-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="31bfa-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-667">TABLE_CATALOG</span></span>|<span data-ttu-id="31bfa-668">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-668">String</span></span>|  
|<span data-ttu-id="31bfa-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="31bfa-670">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-670">String</span></span>|  
|<span data-ttu-id="31bfa-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-671">TABLE_NAME</span></span>|<span data-ttu-id="31bfa-672">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-672">String</span></span>|  
|<span data-ttu-id="31bfa-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31bfa-673">INDEX_CATALOG</span></span>|<span data-ttu-id="31bfa-674">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-674">String</span></span>|  
|<span data-ttu-id="31bfa-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="31bfa-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="31bfa-676">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-676">String</span></span>|  
|<span data-ttu-id="31bfa-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-677">INDEX_NAME</span></span>|<span data-ttu-id="31bfa-678">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-678">String</span></span>|  
|<span data-ttu-id="31bfa-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="31bfa-679">PRIMARY_KEY</span></span>|<span data-ttu-id="31bfa-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-680">Boolean</span></span>|  
|<span data-ttu-id="31bfa-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="31bfa-681">UNIQUE</span></span>|<span data-ttu-id="31bfa-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-682">Boolean</span></span>|  
|<span data-ttu-id="31bfa-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="31bfa-683">CLUSTERED</span></span>|<span data-ttu-id="31bfa-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-684">Boolean</span></span>|  
|<span data-ttu-id="31bfa-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="31bfa-685">TYPE</span></span>|<span data-ttu-id="31bfa-686">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-686">Int32</span></span>|  
|<span data-ttu-id="31bfa-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="31bfa-687">FILL_FACTOR</span></span>|<span data-ttu-id="31bfa-688">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-688">Int32</span></span>|  
|<span data-ttu-id="31bfa-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="31bfa-689">INITIAL_SIZE</span></span>|<span data-ttu-id="31bfa-690">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-690">Int32</span></span>|  
|<span data-ttu-id="31bfa-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="31bfa-691">NULLS</span></span>|<span data-ttu-id="31bfa-692">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-692">Int32</span></span>|  
|<span data-ttu-id="31bfa-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="31bfa-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="31bfa-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-694">Boolean</span></span>|  
|<span data-ttu-id="31bfa-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="31bfa-695">AUTO_UPDATE</span></span>|<span data-ttu-id="31bfa-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-696">Boolean</span></span>|  
|<span data-ttu-id="31bfa-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-697">NULL_COLLATION</span></span>|<span data-ttu-id="31bfa-698">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-698">Int32</span></span>|  
|<span data-ttu-id="31bfa-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="31bfa-700">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-700">Int64</span></span>|  
|<span data-ttu-id="31bfa-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="31bfa-701">COLUMN_NAME</span></span>|<span data-ttu-id="31bfa-702">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-702">String</span></span>|  
|<span data-ttu-id="31bfa-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-703">COLUMN_GUID</span></span>|<span data-ttu-id="31bfa-704">GUID</span><span class="sxs-lookup"><span data-stu-id="31bfa-704">Guid</span></span>|  
|<span data-ttu-id="31bfa-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="31bfa-705">COLUMN_PROPID</span></span>|<span data-ttu-id="31bfa-706">Int64</span><span class="sxs-lookup"><span data-stu-id="31bfa-706">Int64</span></span>|  
|<span data-ttu-id="31bfa-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="31bfa-707">COLLATION</span></span>|<span data-ttu-id="31bfa-708">Int16</span><span class="sxs-lookup"><span data-stu-id="31bfa-708">Int16</span></span>|  
|<span data-ttu-id="31bfa-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="31bfa-709">CARDINALITY</span></span>|<span data-ttu-id="31bfa-710">Decimale</span><span class="sxs-lookup"><span data-stu-id="31bfa-710">Decimal</span></span>|  
|<span data-ttu-id="31bfa-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="31bfa-711">PAGES</span></span>|<span data-ttu-id="31bfa-712">Int32</span><span class="sxs-lookup"><span data-stu-id="31bfa-712">Int32</span></span>|  
|<span data-ttu-id="31bfa-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="31bfa-713">FILTER_CONDITION</span></span>|<span data-ttu-id="31bfa-714">Stringa</span><span class="sxs-lookup"><span data-stu-id="31bfa-714">String</span></span>|  
|<span data-ttu-id="31bfa-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="31bfa-715">INTEGRATED</span></span>|<span data-ttu-id="31bfa-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="31bfa-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31bfa-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31bfa-717">See also</span></span>

- [<span data-ttu-id="31bfa-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="31bfa-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
