# TypeScript Utility Types

- <https://www.youtube.com/watch?v=EU0TB_8KHpY>

* <https://codesandbox.io/s/typescript-utility-types-8j9cfy>

```bash
type User = {
  id: string;
  name: string;
  age: number;
};

type PartialUser = Partial<User>;

type RequiredUser = Required<User>;

type OmitUser = Omit<User, "id" | "name">;

type PickUser = Pick<User, "id" | "name">;

type PartiallyPickedUser = Partial<Pick<User, "id" | "name">>;

type ReadonlyUser = Readonly<User>;

type Mutable<T> = {
  -readonly [K in keyof T]: T[K];
};

type MutableUser = Mutable<User>;

type Role = "admin" | "user" | "anonymous";

type NonAdminRole = Exclude<Role, "admin" | "anonymous">;

type RoleAttributes =
  | { role: "admin"; orgId: string }
  | { role: "user" }
  | { role: "anonymous" };

type AdminRole = Extract<
  RoleAttributes,
  {
    role: "admin";
  }
>;

type Func = (a: number, b: string) => number;

type ReturnValue = ReturnType<Func>;

type Params = Parameters<Func>;

type MaybeString = string | null | undefined;

type DefinitelyString = NonNullable<MaybeString>;

type PromiseString = Promise<string>;

type Result = Awaited<PromiseString>;

const func = async () => {
  return {
    id: 123
  };
};

type Result2 = Awaited<ReturnType<typeof func>>;
```
