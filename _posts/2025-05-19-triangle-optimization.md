---
title: "Challenge Problem - Right Triangle Optimization"
date: 2025-05-20
---
<head>
	<script type="text/javascript" async 
	src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?
	config=TeX-AMS-MML_HTMLorMML"></script>
	<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-6742417150601345"
     crossorigin="anonymous"></script>
</head>
Hello, I hope you're doing well today. Making the distributive property post reminded me of a previous attempt I'd had to make a blog post about a math subject, in particular about a question a friend of mine asked me. Something I find special about the question is that it actually came up as a result of a practical problem he'd encountered while working as a busser at a restaurant, rather than just pure mathematical inquiry, and it ends up tugging at a lot of interesting threads from different fields of math.<br><br>

The question was:
<blockquote>Given a certain length for the hypotenuse, which right triangle has the largest area?</blockquote>

and I solved it two different ways, once in a more analytical fashion (originally using calculus, but while writing this article I realized it can be made precalc-friendly) and then another time with more elementary high school geometry tools. If either of those are within your skillset, I would recommend trying to answer the question for yourself. It's pretty easy to get an educated guess on what the answer should be, but try to see if you can create a convincing mathematical argument for why that answer <i>has</i> to be correct: a high-quality proof should leave very little room for reasonable doubt.<br><br>

I'll give hints leading to my solutions if you feel like you're stuck, or if you'd just like to take a look, but don't feel like you have to stay exactly on the path I took to find my solutions: part of the reason why I wanted to present this problem is that it led me to two very different approaches, so I'm sure other very interesting methods exist which I didn't find, and I would love to hear them if you would like to share.

- <details>
  <summary>
    Analytical method hints
  </summary>
  It might help to start by categorizing what <i>kind</i> of problem we're looking at. We want to know about maximizing the area of our triangle, so we can broadly categorize this as an optimization problem. (And if you'd like, since we have a constraint regarding the hypotenuse, this can specifically be thought of as constrained optimization.)<br>
  One way to handle an optimization problem like this is to start by finding a function which represents the value we're trying to minimize or maximize (called our "objective function") over all of the different choices we could make. This idea of getting the information we want by studying the properties of functions is what I meant when I called these approaches "analytical."<br>
  So, what other information about the triangle are we trying to determine? And how can we express the area in terms of that unknown information? At first, this seemed like an obvious choice to me, which led me to my calculus-based solution, which is what I'll put in my first set of hints, but like I mentioned before there is also a method that doesn't require calculus, if we make a slightly different choice. I'll put that in the second set of hints.
  <details>
    <summary>
      Calculus method setup hints
    </summary>
    Well, we know we have a right triangle with a specific hypotenuse, so something I find fairly natural is to try to proceed by defining the other two sides of the triangle: a triangle has three sides after all. So let's say that we can choose side lengths a and b for the two legs of our triangle.<br>
    Now, for any side lengths a and b that we have in a specific triangle, we can find the area using our typical formula for area of a triangle: $$A = \frac12(\text{base})\cdot(\text{height}) = \frac12 ab$$
    So, if our goal was just to maximize this area function, it might seem like there should be no maximum because we could just make a and b as large as we'd like. So, why can't we just make a and b arbitrarily large? That has to do with our constraint: there's a specific value of the hypotenuse that we need to keep constant. Let's call that c. As we know, the legs and the hypotenuse have to be related via the Pythagorean theorem:$$a^2 + b^2 = c^2$$
    So, now we have our objective function and a constraint function defined in terms of our unknowns a and b. From here, it's just a matter of technique. My original solution involves using multivariable calculus techniques, but there's also a way to proceed with single-variable calculus, so I'll also include that: feel free to check against either solution. <br>
    <details>
      <summary>
        Multivariable calculus solution
      </summary>
      This solution uses a method known as the method of Lagrange multipliers, which I do intend to explain in further depth at some point if I end up making math content more regularly, but this post is already getting fairly long, so today isn't going to be the day. (I may come back and link an explanation if I make one later though.)<br>
      The bottom line is, we can take our objective function and our constraint function in terms of a and b, and state that their gradients (the vectors keeping track of the rates of change of the function) must be parallel, so that the objective function can't change instantaneously without also changing the constraint function, which we know has to be kept constant. This leads us to
      $$\nabla (\frac12 ab) = \lambda \nabla (a^2 + b^2) \Leftrightarrow \langle\frac12 b, \frac12 a\rangle = \lambda \langle 2a, 2b\rangle$$
      $$b = 4\lambda a, a = 4\lambda b \Rightarrow b = 16\lambda^2 b \Rightarrow b(16\lambda^2 - 1) = 0$$
      So, this leaves us with three options: b could be zero, but this doesn't really give us a triangle, we'd have zero area. That leaves us with the two possible values for the multiplier, but if that multiplier is negative then a and b can't both be positive, so it must be true that 
        $$\lambda = \frac14 \Rightarrow a = b$$
        so our answer is that the maximum area must be achieved by constructing the isosceles right triangle.
    </details>
    <details>
      <summary>
        Single-variable calculus solution
      </summary>
      To solve a problem like this with single-variable calculus, we need to solve the constraint equation for one of our variables, so that we can put our objective function in terms of one variable. So, keeping in mind that our side lengths have to be positive, notice that
	$$a^2 + b^2 = c^2 \Rightarrow a = \sqrt{c^2 - b^2}$$
	$$A(b) = \frac12 b \sqrt{c^2 - b^2}$$
	This is a differentiable function in terms of b whenever b is less than c (which is true for all of our non-degenerate triangles) so in order for it to have a maximum or a minimum value at a specific value of b, it must be true that the derivative at that point is 0. Otherwise, consider that if the derivative was positive, increasing b should increase the function, and decreasing b should decrease the function, so a point with a positive derivative has to be less than the values to its right (so it can't be a maximum) and more than the values to its left. (so it can't be a minimum) A similar argument exists for points where the derivative is negative. So, looking for points with zero derivative:
	$$A'(b) = 0 \Rightarrow \frac12 \sqrt{c^2 - b^2} + \frac12 b \cdot \frac1{2\sqrt{c^2 - b^2}} \cdot (-2b) = 0$$
	After cleaning up a bit, and multiplying by 2 and the square root expression on both sides to get rid of the fractions, we can obtain
	$$(\sqrt{c^2 - b^2})^2 - b^2 = 0 \Rightarrow c^2 - 2b^2 = 0 \Rightarrow c^2 = 2b^2 \Rightarrow b = \frac{c}{\sqrt{2}}$$
	which we can plug back into the Pythagorean theorem constraint to get a value for a:
	$$a = \sqrt{c^2 - \frac{c^2}2} = \sqrt{\frac{c^2}2} = \frac{c}{\sqrt{2}}$$
	which shows us that the triangle we're looking for is the isosceles right triangle: a right triangle where the two legs are equal.
    </details>
  </details>
	<details>
		<summary>
			Precalculus method (requires trigonometry)
	 	</summary>
		Remember that it always takes three pieces of information to uniquely define a triangle: think about our congruency rules of SSS, SAS, AAS, and ASA, they all require three pieces of information. Here, our constraint on the hypotenuse is defining one of the side lengths for us, and we know that the angle across from that hypotenuse is a right angle, so that's defining an angle, for a second piece of information. So, we really just need one more piece of information to fully determine the triangle, which means we can think about there just being one more "choice" left to be made. For our purposes, it'll be convenient to think about choosing a value for one of the two other angles in the triangle.<br>
		So if these two angles and a side are enough to uniquely determine the rest of the triangle, we should be able to solve for the other components of the triangle now: in particular, since we're dealing with a right triangle, we can find the lengths of the legs of the triangle using right-triangle trig, also known as "SOHCAHTOA." Let's say a is the length of the leg adjacent to our angle, and b is the length of the leg opposite our angle:
		$$\cos(\theta) = \frac{\text{adjacent}}{\text{hypotenuse}} = \frac{a}{c} \Rightarrow a = c\cos(\theta)$$
		$$\sin(\theta) = \frac{\text{opposite}}{\text{hypotenuse}} = \frac{b}{c} \Rightarrow b = c\sin(\theta)$$
		So, using our formula for area of a triangle, we get
		$$A = \frac12 (\text{base}) (\text{height}) = \frac12 (c \cos(\theta))(c \sin(\theta)) = \frac12 c^2 \cos(\theta) \sin(\theta)$$
		So now, we're tasked with finding what value of our angle will maximize this area. This can be accomplished with standard tools in calculus, but there's also a trick which lets us optimize this function without calculus: can you find it? <br>
		<details>
			<summary>
				Precalculus optimization of the area function
			</summary>
			Recall the double-angle formula for sine:
			$$\sin(2\theta) = 2\cos(\theta)\sin(\theta)$$
			So, applying that to our formula for area, we get
			$$A = \frac14 c^2 \sin(2\theta)$$
			and the maximum occurs when the result of that sine is 1, which will happen when
			$$2\theta = 90^\circ \Rightarrow \theta = 45^\circ$$
			which tells us that our optimal solution is the isosceles, 45-90-45, right triangle. (To anyone going through all of the solutions, bonus points if you can see how this double angle relates to the more purely geometric solution.)
	 	</details>
	</details>

- <details>
  <summary>
    Geometry method hints
  </summary>
	We know that our hypotenuse is going to be held constant, so try drawing out a line segment to stand in for it. Now, if we hold this line segment in place, we can think of that as meaning we've placed two of the three vertices defining our triangle, and we can complete the triangle by placing a third vertex on the plane. That said, not every point we choose will result in a right triangle: something interesting ends up being true about the points which do give us right triangles. Can you find it? <br>
	<details>
		<summary>
			Finishing our right triangle
		</summary>
		There's an interesting circle theorem known as Thales' theorem which can help us here: if one of the sides of a triangle is the diameter of a circle, and the remaining point is a point on that circle, then the angle opposite the diameter is always a right angle. I think including an explanation of exactly why this is the case is a bit more than what I'm trying to do for this post (if you didn't see, there was a lot I had to get into for the analytic methods) so if you'd like to investigate this further, I would recommend Michael Stevens' video on the topic at https://youtu.be/pJwRsoxe3VE?si=IWw6pYa5hDEZShAL for some explanation, as well as great insight into the nuts and bolts of Euclidean geometry.<br>
		(Sorry for the unformatted link, Markdown has decided to punish me for my hubris and just give up on doing certain parts of its job.)<br>
		So, because choosing any of those points on the circle will always result in a right triangle, and that process takes us through every possible value for the other angles of our triangle, we can also say that any right triangle we can build from that hypotenuse will result in the third vertex being on the circle. Can we capitalize on this? <br>
		<details>
			<summary>
				Capitalizing on this
			</summary>
			So first, remember that our goal is to get the largest area possible, and refer to our formula for area of a triangle:
			$$A = \frac12 (\text{base}) (\text{height})$$
			Often with a right triangle, it makes most sense to make one of the legs the base and one of them the height, but we don't have to do it this way. In our case, we can make our static hypotenuse the base, and then think about altitudes drawn perpendicular to the base. Notice that if we do this, the only variable in the area formula is that height: that means that finding the maximum area is exactly the same as finding the maximum height.<br>
			Now in order to find the maximum height, it'll help to get some names for our key points. (I might add a diagram for this at some point, but for now you'll have to draw a diagram yourself and follow along.) Let's call our hypotenuse (and diameter of the circle) line segment AB, with the endpoints A and B being points on the circle. We'll call the center of the circle (and midpoint of AB) point O. Now, let's say that C is the third point of the triangle, the vertex of the right angle in our right triangle, which also has to be a point on the circle. The altitude we care about can be found by drawing a line segment starting at point C toward AB, perpendicular to AB, until they intersect. Call this point of intersection point D.<br>
			So, the altitude we're trying to maximize is CD, but notice that it's a leg of right triangle OCD, so it can never be longer than OC, the hypotenuse of that triangle. OC goes from the center of the circle to a point on the circle, so it's also a radius of the circle. So, it's clear that the altitude of our triangle can never be longer than the radius, so if we can draw a triangle where the altitude is exactly the radius, then that must be the triangle with maximum altitude.<br>
			We can accomplish this by placing C such that OC itself is perpendicular to AB: OC is now both a radius of the circle, and the altitude of our triangle. Now, notice that because OA, OB, and OC are all radii of the circle, they all must be congruent, and angles AOC and BOC are both right angles. As a result of this, triangles AOC and BOC are SAS congruent, so it must be true that AC and BC are congruent. This means that our triangle ABC is an isosceles right triangle, also known as a 45-90-45 triangle, where the lengths of the two legs are the same.
		</details>
	</details>

---

Wow, that really turned into a bit of a "choose your own adventure" situation: I'm not sure if this is something that I'm going to repeat, but I wanted to show just exactly how many valid ways there are to answer a question like this, as well as show off how there are sometimes tradeoffs between using simpler tools and calculations, and using simpler concepts. Often students ask me what the "easy way" to solve a problem is, and maybe here you have an opinion on which way you think is easiest, but if you ask someone else with a different background they might not agree.

In any case, I think that's enough from me for now, I hope you enjoyed. Have a nice rest of your day.
