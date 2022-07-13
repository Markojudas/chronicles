---
title: Ramblings
date: 2022-07-13 14:36
---

<!-- markdownlint-disable  -->

Middle of the week. I have finally heard back from couple of places I have applied to; all rejections without even a simple interview or coding assessment. I'd be lying if I say that it doesn't suck because it does - a lot. The last few days have been rough and the imposter syndrome has been knocking pretty badly. As you can see the last few posts have been small write-ups on how to set up few things. Those write-ups came to be because I had to read the documentations and search high and low all over the internet (stackoverflow, geeksfogeeks, etc...) to make those technologies work. I read and read so much that I know I'll forget what I did and won't been able to do it again; at least with these write-ups I'll have a place to start. I don't want to make one for **PostgreSQL** because it was a little easier - just configure the file `/var/lib/pgsql/data/pg_hba.conf` and change the `METHOD` from `ident` to `password`; ideally it should be `md5` per documentation but I gotta find how to encrypt the password so it can work with it. I also have to create a user KEEPING IN MIND case sensitivity - all should be lowercase for future reference.

Additionally, I have done several leetcode problems, currently on day 12/15. The last few problems, labeled as "easy" and "medium" were quite challenging in the fact that even the solution provided by leetcode is a bit confusing. I am not familiar with Dynamic Programming and I REALLY need to get better at some algorithms and patterns (i.e., Sliding Window, DFS/BFS, etc...). Even though I feel pretty confident with GO, I struggled creating a 2D slice/array provided the row and column values from the arguments passed to the function.

Not sure if this is the right way to do it; the documentation found shows a different way without the calls to `make` within the loop.

<pre><code>func create2DSlice(r, c int) [][]int {

	newMDS := make([][]int, r)

	for idx := range newMDS {
		newMDS[idx] = make([]int, c)
	}

	return newMDS
}</code></pre>

TLDR: I have the blues.
