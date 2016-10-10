;; Constraint definitions for the Broadcom Videocore IV
;; Copyright (C) 2011-2013 Free Software Foundation, Inc.

;; This file is part of GCC.

;; GCC is free software; you can redistribute it and/or modify
;; it under the terms of the GNU General Public License as published by
;; the Free Software Foundation; either version 3, or (at your option)
;; any later version.

;; GCC is distributed in the hope that it will be useful,
;; but WITHOUT ANY WARRANTY; without even the implied warranty of
;; MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
;; GNU General Public License for more details.

;; You should have received a copy of the GNU General Public License
;; along with GCC; see the file COPYING3.  If not see
;; <http://www.gnu.org/licenses/>.

;; Register constraints.
(define_register_constraint "f" "FAST_REGS"
  "@internal")

;; Integer constraints.
(define_constraint "I"
  "A 5-bit unsigned integer in the range 0 to 31, mostly used in ALU ops."
  (and (match_code "const_int")
       (match_test "IN_RANGE (ival, 0, 31)")))

(define_constraint "J"
  "An 6-bit signed integer in the range -32 to 31, used by div ops."
  (and (match_code "const_int")
       (match_test "IN_RANGE (ival, -32, 31)")))

(define_constraint "K"
  "A 6-bit unsigned integer in the rand 0 to 63, used by comparison ops."
  (and (match_code "const_int")
       (match_test "IN_RANGE (ival, 0, 63)")))

(define_constraint "L"
  "A signed integer in the range -1024 to 1023, used by index memory ops."
  (and (match_code "const_int")
       (match_test "IN_RANGE (ival, -1024, 1023)")))

(define_constraint "M"
  "An unsigned integer in the range 0 to 60, used by the short-form memory
   ops."
  (and (match_code "const_int")
       (match_test "IN_RANGE (ival, 0, 60)")))


