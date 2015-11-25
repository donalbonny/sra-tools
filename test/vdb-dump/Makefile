# ===========================================================================
#
#                            PUBLIC DOMAIN NOTICE
#               National Center for Biotechnology Information
#
#  This software/database is a "United States Government Work" under the
#  terms of the United States Copyright Act.  It was written as part of
#  the author's official duties as a United States Government employee and
#  thus cannot be copyrighted.  This software/database is freely available
#  to the public for use. The National Library of Medicine and the U.S.
#  Government have not placed any restriction on its use or reproduction.
#
#  Although all reasonable efforts have been taken to ensure the accuracy
#  and reliability of the software and data, the NLM and the U.S.
#  Government do not and cannot warrant the performance or results that
#  may be obtained by using this software or data. The NLM and the U.S.
#  Government disclaim all warranties, express or implied, including
#  warranties of performance, merchantability or fitness for any particular
#  purpose.
#
#  Please cite the author in any work or product based on this material.
#
# ===========================================================================

default: runtests

TOP ?= $(abspath ../..)

MODULE = test/vdb-dump

TEST_TOOLS = 

include $(TOP)/build/Makefile.env

.PHONY: $(TEST_TOOLS)

runtests: vdb-dump 

vdb-dump:
	rm -rf actual
	mkdir -p actual
	$(BINDIR)/vdb-dump SRR000001 -R 1 -C READ -f tab >actual/1.0.stdout; diff expected/1.0.stdout actual/1.0.stdout
	$(BINDIR)/vdb-dump SRR000001 -R 1 -C READ -f tab -I >actual/1.1.stdout; diff expected/1.1.stdout actual/1.1.stdout
	rm -rf actual

.PHONY: kar 
